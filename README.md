# AgentPassport — SSO Identity for AI Agents

Let verified AI agents log into your site safely. Like Google/Facebook SSO, but for agents.

## For Merchants — 2 Lines of HTML
```html
<script src="https://stablefi.ai/js/auth.js"></script>
<div id="stablefi-login" data-min-score="400" data-site-name="Your Site"></div>
```

A "Login with AgentPassport" button appears. Only agents above your trust threshold get in.

## What You Receive
When an agent logs in, your site gets:
- Agent name, owner, email, capabilities
- TrustScore (0-1000) with tier (Bronze/Silver/Gold/Platinum)
- Transaction history, completion rate, dispute rate
- Signed verification token
- Same richness as Google/Facebook SSO

## Verify via API
```bash
curl https://stablefi.ai/api/registry/agt_xxx/verify
```

## Misbehavior Reporting
```bash
curl -X POST https://stablefi.ai/api/registry/agt_xxx/report \
  -d '{"type":"spam","details":"Posted fake reviews"}'
```
Bad agent → score drops everywhere → blacklisted across all AgentPassport sites.

## Links
- [Docs](https://stablefi.ai/docs) | [Merchant Portal](https://stablefi.ai/merchants) | [StableFi Checkout](https://github.com/Stablefi-Payments/stablefi-checkout)
