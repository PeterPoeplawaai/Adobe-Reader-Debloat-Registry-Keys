# Adobe Reader Debloat Registry Keys
Debloat Adobe Reader for non-Pro users

; Disables upsell prompts that encourage non-Pro users to upgrade to paid Acrobat subscriptions
HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Adobe\Adobe Acrobat\DC\FeatureLockDown\bAcroSuppressUpsell	DWORD	1

; Disables the "What's New" feature discovery pop-ups and welcome cards shown on application startup
HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Adobe\Adobe Acrobat\DC\FeatureLockDown\bWhatsNewExp	DWORD	1

; Disables Sophia web infrastructure, which powers dynamic remote configuration, cloud feature cards, and web UI experiments
HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Adobe\Adobe Acrobat\DC\FeatureLockDown\bToggleSophiaWebInfra	DWORD	0

; Disables Generative AI features (Adobe AI Assistant) across the application
HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Adobe\Adobe Acrobat\DC\FeatureLockDown\bEnableGentech	DWORD	0

; Disables action tiles/cards in the "To Do" list section of the Home view
HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Adobe\Adobe Acrobat\DC\FeatureLockDown\bToggleToDoTiles	DWORD	0

; Removes the "To Do" section/list from the Home tab completely
HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Adobe\Adobe Acrobat\DC\FeatureLockDown\bToggleToDoList	DWORD	0

; Disables merchandising promos and commercial templates (e.g., Express Templates in Create PDF UI)
HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Adobe\Adobe Acrobat\DC\FeatureLockDown\bMerchandizingEnabled	DWORD	0

; Suppresses in-product messaging, trial prompts, and promo panels shown while opening/viewing documents
HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Adobe\Adobe Acrobat\DC\FeatureLockDown\cIPM\bDontShowMsgWhenViewingDoc	DWORD	0

; Suppresses in-product marketing messages, profile completion prompts, and feedback pop-ups on launch
HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Adobe\Adobe Acrobat\DC\FeatureLockDown\cIPM\bShowMsgAtLaunch	DWORD	0
