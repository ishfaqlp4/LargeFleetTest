<style type='text/css'>
	.embeddedServiceHelpButton .helpButton .uiButton {
		background-color: #005290;
		font-family: "Arial", sans-serif;
	}
	.embeddedServiceHelpButton .helpButton .uiButton:focus {
		outline: 1px solid #005290;
	}
</style>

<script type='text/javascript' src='https://service.force.com/embeddedservice/5.0/esw.min.js'></script>
<script type='text/javascript'>
	var initESW = function(gslbBaseURL) {
		embedded_svc.settings.displayHelpButton = true; //Or false
		embedded_svc.settings.language = ''; //For example, enter 'en' or 'en-US'

		//embedded_svc.settings.defaultMinimizedText = '...'; //(Defaults to Chat with an Expert)
		//embedded_svc.settings.disabledMinimizedText = '...'; //(Defaults to Agent Offline)

		//embedded_svc.settings.loadingText = ''; //(Defaults to Loading)
		//embedded_svc.settings.storageDomain = 'yourdomain.com'; //(Sets the domain for your deployment so that visitors can navigate subdomains during a chat session)

		// Settings for Chat
		//embedded_svc.settings.directToButtonRouting = function(prechatFormData) {
			// Dynamically changes the button ID based on what the visitor enters in the pre-chat form.
			// Returns a valid button ID.
		//};
		//embedded_svc.settings.prepopulatedPrechatFields = {}; //Sets the auto-population of pre-chat form fields
		//embedded_svc.settings.fallbackRouting = []; //An array of button IDs, user IDs, or userId_buttonId
		//embedded_svc.settings.offlineSupportMinimizedText = '...'; //(Defaults to Contact Us)

// Wex Coupon Code capture code from Einstein Bot
//Hardcoding coupon cookies to the site... DO NOT ADD THIS TO PROD DEPLOYMENT!!
		
    document.cookie = "wex_cc_session=EDH2|W7CP|M41728";
    document.cookie = "wex_cc_persistent=H1F|W7CP|EDH4|M41728";

//Retrieve all cookies
var x = document.cookie;
var cookieValue='';
var foundInSession = false; //Variable to track if value is found in wex_cc_session
    console.log(x); //log all cookies
    
	//Split cookies and process each one	 
	x.split(';').forEach(function(el) {
     		var y = el.split('=');
		     console.log(y);
		     console.log(y[1]);
		
//Extract values for specific cookies
// First the code checks for cookieValue in 'wex_cc_session' and if empty it then checks in 'wex_cc_persistent'.
   
	 	if( y[0].trim()==='wex_cc_session' && !foundInSession){
		       	if(y[1]){
		     		 cookieValue = y[1].split('|')[0];
	  			 foundInSession = true; //Exiting the loop once value is found in wex_cc_session
		       	}
      
      		}
		if(y[0].trim()==='wex_cc_persistent') {
 		if(y[1]){
     		 	cookieValue = y[1].split('|')[0];
      		 }
		}
 	  	
    		console.log(cookieValue);//log extracted cookieValue
	});
 	
   
//  Array to include pre-chat fields and map it to the associated LiveChatTranscript custom field.
		embedded_svc.settings.extraPrechatFormDetails = [{
  		"label": "Coupon Code",
  		"value": cookieValue,
  		"displayToAgent": true,
  		"transcriptFields" : ["Coupon_Code__c"]
		},{
		  "label":"First Name",  
		  "transcriptFields": ["FirstName__c"]
		},{
		  "label":"Last Name", 
		  "transcriptFields": ["LastName__c"]
		},{
		  "label":"Email", 
		  "transcriptFields": ["Email__c"]
		},{
		  "label":"Company", 
		  "transcriptFields": ["Company__c"]
		},{
		  "label":"Phone", 
		  "transcriptFields": ["Phone__c"]
		}];
		
		embedded_svc.settings.enabledFeatures = ['LiveAgent'];
		embedded_svc.settings.entryFeature = 'LiveAgent';

		embedded_svc.init(
			'https://wexinc--stagefull.sandbox.my.salesforce.com',
			'https://wexinc--stagefull.sandbox.my.salesforce-sites.com/chat',
			gslbBaseURL,
			'00DU70000003ZkP',
			'Large_Fleet',
			{
				baseLiveAgentContentURL: 'https://c.la2s-core2.sfdc-lywfpd.salesforceliveagent.com/content',
				deploymentId: '5720g00000000Oy',
				buttonId: '573U70000000Nr3',
				baseLiveAgentURL: 'https://d.la2s-core2.sfdc-lywfpd.salesforceliveagent.com/chat',
				eswLiveAgentDevName: 'EmbeddedServiceLiveAgent_Parent04IU70000000673MAA_18d1421fc85',
				isOfflineSupportEnabled: false
			}
		);
	};

	if (!window.embedded_svc) {
		var s = document.createElement('script');
		s.setAttribute('src', 'https://wexinc--stagefull.sandbox.my.salesforce.com/embeddedservice/5.0/esw.min.js');
		s.onload = function() {
			initESW(null);
		};
		document.body.appendChild(s);
	} else {
		initESW('https://service.force.com');
	}
</script>
