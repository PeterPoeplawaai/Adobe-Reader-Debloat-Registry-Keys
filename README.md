# Adobe Reader Debloat Registry Keys
Debloat Adobe Reader for non-Pro users<br><br>

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

<br><br>

Below is the list of essential registry keys and values that must be configured (or explicitly set to allow access) for Pro users to log in successfully:

; Enables Adobe's Identity Management Service (IMS) used for Adobe ID / Enterprise ID authentication
HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Adobe\Adobe Acrobat\DC\FeatureLockDown\cIMS\bEnableIMS	DWORD	1

; Ensures users are allowed to sign out or switch accounts when managing license sessions
HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Adobe\Adobe Acrobat\DC\FeatureLockDown\bDisableSignOut	DWORD	0

; Ensures the Adobe Acrobat Update Service and license sync handshakes are permitted to connect
HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Adobe\Adobe Acrobat\DC\FeatureLockDown\bUpdater	DWORD	1

; Allows enterprise token and subscription verification web calls
HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Adobe\Adobe Acrobat\DC\FeatureLockDown\bToggleSophiaWebInfra	DWORD	1

Important Deployment Notes<br>
Sophia Web Infrastructure (bToggleSophiaWebInfra): While turning this off (0) is common for debloating Reader, setting it to 1 is often necessary for Pro users because the modern sign-in dialog, web-based authentication flows, and dynamic subscription cloud panels rely on Adobe's Sophia web infrastructure to render correctly.

Network Access: Ensure your firewalls or proxy policies do not block endpoints required for licensing, such as *.adobe.com, ims-na1.adobelogin.com, and Adobe's activation servers.
HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Adobe\Adobe Acrobat\DC\FeatureLockDown\cIMS\bEnableIMS	DWORD	1
Summary
Your current list of 9 keys is safe to use for non-Pro/Standard users because it only strips out UI clutter, marketing, AI assistant panels, and upsell prompts. Pro users will still be able to sign in with your current 9 keys, provided that your environment allows outbound communication to Adobe's activation servers (*.adobe.com) and the Identity Management Service (IMS) is not explicitly disabled via cIMS policies.
