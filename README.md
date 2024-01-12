# Cloudflare DNS Auto IP Updater

Use cloudflare API to update IPs when Dynamic IP changes

Python3 is required. The tool currently only works with API tokens but I am working to add the ability to use API keys as well.

This tool will update your cloudflare A records whenever a dynamic IP address change is detected.

Simply add your cloudflare info into the cfauth.ini file and then run the cf-dyn-ip-updater.py file. Make sure your generated API token has DNS edit rights configured properly for your zones or the updates will not work.

If you run cf-dyn-ip-updater.py -q or cf-dyn-ip-updater.py --query it will use the cloudflare API tokens configured for each zone and run a query returning a list of all zone and record ids available. For the query to work properly you must use an API token that has at least read permission for ALL zones. The query will print out the cfauth.ini zone_id, bearer token, and record_id configuration so that you can copy and paste it into the cfauth.ini file.

If this program helps you out then I appreciate any donations!

PayPal: https://paypal.me/JMurley77?locale.x=en_US

Be aware, this only works if your site is on the Cloudflare CDN. See the requirements below:

<h2>Requirements:</h2>

  - Python 3.8 or above
  - Python requests library (install using `pip3 install requests`)
  - A Cloudflare account with website
  - Cloudflare API Bearer Token
  - Need to know your zone ID
  - The ID(s) of the A record(s) you want to change
  
  
<h2>Optional:</h2>

  - SMTP email, to send an update when the IP changes
