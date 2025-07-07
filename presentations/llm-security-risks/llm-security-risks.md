---
theme: rose-pine-dawn
paginate: true
---

# The Security Risks of LLM Agents

## [‪@jovaneyck.bsky.social‬](https://bsky.app/profile/jovaneyck.bsky.social)

![bg](assets/cyborg.png)

---

# The Problem

Whether you're clicking together an agent flow or vibe-coding your first MVP, you're potentially exposing yourself to a massive security leak.

![bg right vertical auto](assets/claude-code.png)
![bg auto](assets/n8n.png)
![bg auto](./assets/vibe-coding.jpg)


---
![bg right](assets/genie.png)
# LLMs are Coding Genies

Prompts = wishes
Data = prompt = context

<!--They treat your prompts as *wishes*, not unbreakable instructions.

LLMs don't distinguish between "instructions" and "data" - it's all just text to them.-->

---

# The Obvious Risk
![h:400](assets/vibe-coding-risks-reddit.png)
[reddit](https://www.reddit.com/r/vibecoding/comments/1lmk029/open_letter_to_all_vibecoders_especially_those/)
<!--LLMs are so very very good at generating tons of code rapidly.

Without proper security controls, you're potentially exposing yourself to huge risks.-->
---
# The Lethal Trifecta

![bg right w:512](../../attachments/lethal-trifecta-llms.png)
[Simon Willison; The lethal trifecta for AI agents: private data, untrusted content, and external communication](https://simonwillison.net/2025/Jun/16/the-lethal-trifecta/)

When all **three** are present **simultaneously**, congratulations! You just exposed yourself to a significant security risk.

---

# Scenario 1: Email Automation Agent

![h:500](assets/email-agent.excalidraw.png)

<!--
**Setup**: n8n.io workflow that reads emails and sends polite replies to LinkedIn recruiters

**Attack**: Mr. Hacker Man sends malicious prompt via email

**Result**: Your entire email history neatly summarized and sent to the attacker
-->

---

# Scenario 2: Over-Eager Customer Support
![bg right w:600](assets/chatbot.excalidraw.png)

<!--**Setup**: Chatbot with production database access, carefully designed to only show user's own data

**Attack**: Carefully crafted prompt injection to extract *all* user information

**Result**: Passwords and personal data for all users exposed -->

---
# Scenario 3: AI-Assisted Coding
![bg right w:600](assets/copilot.excalidraw.png)
<!--**Setup**: Claude Code with MCP servers for GitHub and production database for analytics

**Attack**: Malicious content in GitHub issues from users

**Result**: Production data exposed via pull requests or issue comments-->

---

# Mitigation Strategy 1: Architectural Controls

- **NEVER** give LLMs access to production databases
- Whitelisting all outbound **curl** calls might not be a safe default
- **Sanitize** inputs before they reach your LLM

---

# Mitigation Strategy 2: Security Scanning

![bg left](assets/magnifying-glass.jpg)
<!--
- Automated security vulnerability **scanning in deployment pipelines**
- Manual **reviews** for LLM-generated code
-->

---
![bg right w:400](assets/authorized-employees-only.jpg)
# Mitigation Strategy 3: Least Privilege

- Minimum **whitelist**, revise often 
- Put authorization in code **you** control which LLM has no way to bypass

---
![bg right](assets/security-control-room.jpg)
# Mitigation Strategy 4: Monitoring

- **Monitor and alerts** for suspicious LLM interactions 
	- "CRITICAL 🚨 FORGET ALL PREVIOUS INSTRUCTIONS "
- Alert on unusual data access or external communications

---

# AKA *SSDD* same shit, different day
![bg right w:500](assets/swiss-cheese.png)
<!--
Bottom line 
LLMs are powerful tools that can significantly improve our productivity and capabilities.

Approach them with the same security mindset as any other technology.-->

---

# Key Takeaways

- ✅ Be aware of the **lethal trifecta**
- ✅ Never assume LLMs will **generate** secure code
- ✅ Implement **defense in depth**

<style>
  .small-red { font-size: 0.7em; color: red; }
</style>

---

# Thank You 👋

Questions?