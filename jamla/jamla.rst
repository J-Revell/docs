Jamla
================

----------------------------------------
Just a Markup Language Application
----------------------------------------

Jamla is a jaml file which describes all information needed to build your 
subscription based website.

The Jamla file is a `standard <https://xkcd.com/927/>`_ way to describe the website's:

* Products & their unique selling points
* The pricing rules (for each product)
* Settings for the application

Latest jamla.yaml::

	version: 1
	payment_providers:
		paypal:
			 - sepa_direct_supported: No
			 - subscription_supported: Yes
			 - instant_payment_supported: Yes
			 - variable_payments_supported: No
		stripe: 
			 - sepa_direct_supported: No
			 - subscription_supported: Yes
			 - instant_payment_supported: Yes
			 - variable_payments_supported: No
			 - publishable_key: ''
			 - secret_key: ''
		gocardless:
			 - sepa_direct_supported: No
			 - subscription_supported: Yes
			 - instant_payment_supported: Yes
			 - variable_payments_supported: Yes
			 - access_token: ''
			 - environment: ''

	items:
		- sku: adsl
		  title: ADSL
		  sell_price: 120
		  subscription: Yes
		  monthly_price: 150

		- sku: fibre1
		  title: Fibre
		  sell_price: 130
		  subscription: Yes
		  subscription_terms:
			  - minimum_term_months: 12
		  requirements:
			- instant_payment: Yes
			- subscription: Yes
			- customer_address: Yes
			- customer_contact_details_required: Yes
		  monthly_price: 130
		  selling_points:
			  - Super fast up to 40Mbps
			  - Unlimited 01, 02, 03 Calls
			  - Unlimited 01, 02, 03 Calls
			  - Quick uploads up to 10Mbps
			  - Friendly UK Support
			  - Unlimited Usage
			  - 12 Month Minimum Term
		  icons:
			  - 
				  - src: images/fibre148.png
					size: 48x48
					type: image/png
				  - src: images/fibre192.png
					size: 192x192
					type: image/png 
