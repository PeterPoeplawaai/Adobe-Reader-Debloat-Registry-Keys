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

To ensure Pro users can successfully sign in, make sure your deployment does not include the following restrictions (which are commonly bundled in aggressive debloat scripts):

1. Enable Sign-In and Licensing Services
Ensure these keys are either removed or set to allow authentication:

bUpdater / bEnableAcrobatUpdater (Must not completely disable update/licensing handshakes required for subscription verification).

Sign-in UI / Named User Licensing: Adobe Acrobat Pro relies on Adobe Creative Cloud desktop runtime and browser sign-in handshakes. If you have blocked sign-in dialogs via feature lockdown, users cannot authenticate.

2. Specific Registry Keys to Check
If Pro users are experiencing login loops or "Sign-in required" errors, verify that these keys are not set to block authentication:

Codefragment
; Ensure sign-in and profile synchronization are allowed (should be 0 or deleted)
HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Adobe\Adobe Acrobat\DC\FeatureLockDown\bDisableSignOut	DWORD	0

; Ensure Adobe ID / Enterprise ID login infrastructure is not locked out
HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Adobe\Adobe Acrobat\DC\FeatureLockDown\cIMS\bEnableIMS	DWORD	1
Summary
Your current list of 9 keys is safe to use for non-Pro/Standard users because it only strips out UI clutter, marketing, AI assistant panels, and upsell prompts. Pro users will still be able to sign in with your current 9 keys, provided that your environment allows outbound communication to Adobe's activation servers (*.adobe.com) and the Identity Management Service (IMS) is not explicitly disabled via cIMS policies.
