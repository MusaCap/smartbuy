# 🏁 Sprint Plan – SmartBuy Agent (Windsurf Build)

Each sprint is 2 weeks long and focused on shipping functional, trackable agent capabilities. Tags follow Windsurf conventions for epics, priorities, and agent task tracking.

---

## 🛠️ Sprint 0: Setup & Foundation
**Objective**: Establish core infrastructure and agent skeletons.

### Tasks
- [ ] Set up Windsurf project workspace `@epic:infra @priority:high @status:todo`
- [ ] Define agent schema: SearchAgent, PurchaseAgent, NotificationAgent `@epic:infra @tag:agent @priority:high @status:todo`
- [ ] Implement Google/Email-based user authentication `@epic:auth @priority:high @tag:MVP @status:todo`
- [ ] Create database schema for users, preferences, requests, and orders `@epic:infra @tag:db @priority:high @status:todo`

### Deliverables
- Working Windsurf environment
- Auth system integrated
- Agents initialized
- Schema committed

---

## 📥 Sprint 1: Input Flow + User Preferences
**Objective**: Allow product requests and preference storage.

### Tasks
- [ ] Build request form + chat UI for input `@epic:request @tag:NLP @tag:chatbot @priority:high @status:todo`
- [ ] Capture and persist product requests `@epic:request @tag:backend @priority:high @status:todo`
- [ ] Build user preferences UI (price range, brands, delivery window) `@epic:preferences @tag:UI @priority:medium @status:todo`
- [ ] Link preferences to requests and normalize input `@epic:preferences @tag:MVP @status:todo`

### Deliverables
- Input-to-request pipeline working
- Editable preference system
- Linked requests with context

---

## 🔍 Sprint 2: Product Search & Matching
**Objective**: Enable product search across platforms via agents.

### Tasks
- [ ] Build SearchAgent to fetch product listings from Amazon & Walmart `@epic:search @tag:agent @priority:high @status:todo`
- [ ] Normalize search results and store in ProductMatch `@epic:search @tag:workflow @tag:data @status:todo`
- [ ] Display top matches in dashboard UI `@epic:search @tag:UI @tag:product-info @priority:medium @status:todo`
- [ ] Apply preference filters to suggest best match `@epic:search @tag:logic @status:todo`

### Deliverables
- End-to-end product match demo
- Preference-aware match ranking
- Visual UI for matches

---

## 🛒 Sprint 3: Purchase Automation + Notifications
**Objective**: Complete product purchase and track delivery.

### Tasks
- [ ] Build PurchaseAgent for order placement `@epic:purchase @tag:agent @tag:automation @priority:high @status:todo`
- [ ] Handle fallback if product is unavailable `@epic:purchase @tag:error-handling @priority:medium @status:todo`
- [ ] Build NotificationAgent for order status (via SMS/email) `@epic:notifications @tag:agent @tag:alerts @status:todo`
- [ ] Create order history dashboard `@epic:purchase @tag:UI @tag:history @status:todo`

### Deliverables
- Fully automated purchase flow
- Resilient agent logic
- Live tracking + notification system

---

## 📊 Tracking Tags Guide

Use these tags across tasks to filter and report in Windsurf:

- **Epics**: `@epic:auth`, `@epic:request`, `@epic:search`, `@epic:purchase`, `@epic:notifications`, `@epic:preferences`, `@epic:infra`
- **Priority**: `@priority:high`, `@priority:medium`, `@priority:low`
- **Status**: `@status:todo`, `@status:in-progress`, `@status:done`
- **Special Tags**: `@tag:MVP`, `@tag:agent`, `@tag:UI`, `@tag:workflow`, `@tag:chatbot`, `@tag:NLP`, `@tag:db`, `@tag:automation`, `@tag:alerts`, `@tag:error-handling`

---

## 🧾 Export Options

- To Notion: Paste this markdown into a page and convert checkboxes into tasks.
- To Windsurf: Use this format to generate agents & tasks directly.
- To GitHub Projects: Copy into `.md` file and link to GitHub issues.

