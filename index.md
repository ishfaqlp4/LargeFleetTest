<html>
	<head>
		<meta name="viewport" content="width=device-width, initial-scale=1, minimum-scale=1">
		
	</head>
 <body><style type='text/css'>
	.embeddedServiceHelpButton .helpButton .uiButton {
		background-color: #005290;
		font-family: "Arial", sans-serif;
	}
	.embeddedServiceHelpButton .helpButton .uiButton:focus {
		outline: 1px solid #005290;
	}
</style>
<script type='text/javascript' src='https://c.la2s-core2.sfdc-lywfpd.salesforceliveagent.com/content/g/js/60.0/deployment.js'></script>
<script type='text/javascript'>
liveagent.init('https://d.la2s-core2.sfdc-lywfpd.salesforceliveagent.com/chat', '5720g00000000Oy', '00DU70000003ZkP');
</script>
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

		embedded_svc.settings.enabledFeatures = ['LiveAgent'];
		embedded_svc.settings.entryFeature = 'LiveAgent';

		embedded_svc.init(
			'https://wexinc--stagefull.sandbox.my.salesforce.com',
			'https://wexinc--stagefull.sandbox.my.site.com/CustomerCommunity',
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
</body>
</html>
