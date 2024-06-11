SCIM Endpoint: https://xfour.cloudflareaccess.com/scim/804ec8e6-2260-44bc-8196-1063d4f2a1bd
SCIM Secret: 7da302fc2265f81afaa4bb2dd70d0c3c23cf0b5bf2a0372f497505d745f7281a

# Source of Truth
Unsure if we should use CloudFlare zero-trust (CF0T) or Entra as source of truth
- [x] Identify source of truth (Entra/ CF0T)
CloudFlare is likely to be a very long-term provider. They offer low/ no cost services and have the best domain rates around. The decision to use CloudFlare is not feature-dependent, it is solely cost dependent. 
Entra is established and already used within the org. However, if we move away from the M365 suite of products we may end up paying for a service we don't need. 
## Unknowns
- What is the CF0T pricing model? 
	- 
- Is Proton compatible with SSO? 
	- 
## Entra
- [x] Setup CF0T
- [x] Link CF0T to Entra
# SSO Services
These are split into two categories. Services that are already in use, but with no SSO and services that need to be provisioned wholely. 
## New
- [ ] Google Workspaces (Entra)
## Existing
- [ ] Proton
- [ ] Webflow