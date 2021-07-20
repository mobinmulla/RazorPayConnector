# RazorPay Connector
Razorpay connector is used to integrate Payment API using Razorpay gateway.

If you are using Mendix 8.#.# version then download module from marketplace.
https://marketplace.mendix.com/link/component/112128

The converted module for Mendix 9.0.5 is available on below link
https://drive.google.com/file/d/1MeIPZIIkhrmOze3JbfBowl_AfZlk3qev/view?usp=sharing

After importing this module in your Project you need to follow the following steps:
1. Login on https://razorpay.com/  If you dont have account please create new one.
2. Use test mode for testing purpose,. You can see mode on the top side on the dashboard.
3. Generate API key. In order to do that go to the settings, in setting you can find API Key section.
4. Download API Key.
5. Add downloaded API Key file in the resource directory of your project. so that the API key get accessable to the system.

Mendix side changes:
1. Add CMI_RZP_Microflow_Authentication microflow to the After Startup microflow.
2. Call the nanoflow CMI_RZP_Nanoflow_MakePayment from your page through a button, or from another nanoflow. 
   This nanoflow needs the entities RazorPayConnector.CMI_RZP_Customer and RazorPayConnector.CMI_RZP_Order to be filled and sent as parameters.
3. In the microflow CMI_RZP_Microflow_Authentication, change your company details in the activity ‘Create Object RazorPayConnector.CMI_RZP_Company’ to add your company name.
4. Pass correct values in the JavaScript Action "CMI_RZP_JSAction_Prefill_Checkout".

While calling the service if you are facing "Rayzorpay not define" and "Rayzorpay is not constructor" error then add script in index.html file in the head tag.
      Script:
      <script src="https://checkout.razorpay.com/v1/checkout.js"></script>
      
NOTE: Refer integration document of RazorPay API Integration. 
      
