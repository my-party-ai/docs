# FastParty Documentation — Mintlify Build Spec

> **Instructions for Claude Code:** This file is a complete specification for building the FastParty product documentation site using Mintlify. Follow the file structure, page content, and configuration exactly as described. Create every file listed. Where content is marked with `[CONTENT]` blocks, write it fully — do not leave placeholders. Use the Mintlify MDX format throughout.

---

## 1. Project Overview

**Product:** FastParty — an AI-native event planning platform  
**Website:** fastparty.ai  
**App:** app.fastparty.ai  
**Docs subdomain:** docs.fastparty.ai  
**Support:** support@fastparty.ai  
**Docs framework:** Mintlify  
**AI Concierge name:** Antsy  
**Platforms:** iOS, Android, Web  

FastParty is an AI-native event planning platform. Its core value proposition is that users can plan, manage, and coordinate every aspect of an event — guests, agendas, food, potlucks, tasks — through natural conversation with AI, without navigating complex menus or forms. FastParty also integrates with Claude AI via its MCP (Model Context Protocol) server, allowing users to manage events directly from Claude.

---

## 2. Mintlify Configuration

### `mint.json`

```json
{
  "name": "FastParty",
  "logo": {
    "light": "/logo/light.svg",
    "dark": "/logo/dark.svg"
  },
  "favicon": "/favicon.png",
  "colors": {
    "primary": "#1A6B9A",
    "light": "#4A9EC4",
    "dark": "#0D3E5C"
  },
  "topbarLinks": [
    { "name": "App", "url": "https://app.fastparty.ai" },
    { "name": "Support", "url": "mailto:support@fastparty.ai" }
  ],
  "topbarCtaButton": {
    "name": "Get Started Free",
    "url": "https://app.fastparty.ai/signup"
  },
  "anchors": [
    {
      "name": "Claude AI Integration",
      "icon": "robot",
      "url": "claude-integration"
    },
    {
      "name": "Support",
      "icon": "envelope",
      "url": "mailto:support@fastparty.ai"
    },
    {
      "name": "FastParty App",
      "icon": "arrow-up-right-from-square",
      "url": "https://app.fastparty.ai"
    }
  ],
  "navigation": [
    {
      "group": "Getting Started",
      "pages": [
        "introduction",
        "quickstart",
        "platforms"
      ]
    },
    {
      "group": "Core Features",
      "pages": [
        "features/events",
        "features/guests",
        "features/agenda",
        "features/food-and-beverage",
        "features/potluck",
        "features/tasks",
        "features/circles",
        "features/antsy-ai"
      ]
    },
    {
      "group": "Claude AI Integration",
      "pages": [
        "claude-integration/overview",
        "claude-integration/connect",
        "claude-integration/what-you-can-do",
        "claude-integration/example-prompts",
        "claude-integration/faq"
      ]
    },
    {
      "group": "Account & Settings",
      "pages": [
        "account/profile",
        "account/notifications",
        "account/billing",
        "account/security"
      ]
    },
    {
      "group": "Troubleshooting",
      "pages": [
        "troubleshooting/common-issues",
        "troubleshooting/contact-support"
      ]
    }
  ],
  "footerSocials": {
    "instagram": "https://instagram.com/fastpartyai",
    "linkedin": "https://linkedin.com/company/fastparty"
  }
}
```

---

## 3. File Structure to Create

```
docs/
├── mint.json
├── introduction.mdx
├── quickstart.mdx
├── platforms.mdx
├── features/
│   ├── events.mdx
│   ├── guests.mdx
│   ├── agenda.mdx
│   ├── food-and-beverage.mdx
│   ├── potluck.mdx
│   ├── tasks.mdx
│   ├── circles.mdx
│   └── antsy-ai.mdx
├── claude-integration/
│   ├── overview.mdx
│   ├── connect.mdx
│   ├── what-you-can-do.mdx
│   ├── example-prompts.mdx
│   └── faq.mdx
├── account/
│   ├── profile.mdx
│   ├── notifications.mdx
│   ├── billing.mdx
│   └── security.mdx
└── troubleshooting/
    ├── common-issues.mdx
    └── contact-support.mdx
```

---

## 4. Page-by-Page Content Specification

---

### `introduction.mdx`

**Title:** Welcome to FastParty  
**Description:** FastParty is the AI-native event planning platform  

Write a warm, energetic introduction page that covers:

- What FastParty is: an AI-native event planning platform available on iOS, Android, and web
- The core idea: plan any event — birthday parties, potlucks, work gatherings, dinners — through natural conversation with AI, without complex forms or menus
- Introduce Antsy, FastParty's built-in AI concierge, who helps users plan events conversationally inside the app
- Mention the Claude AI integration: FastParty also works directly inside Claude via the Claude Connector Store, so users can manage events without ever opening the FastParty app
- A "Where to start" card group pointing to: Quickstart, Features overview, and Claude Integration

Use a `<CardGroup cols={2}>` with cards for:
- **Create Your First Event** → `/quickstart`
- **Explore Features** → `/features/events`
- **Use FastParty in Claude** → `/claude-integration/overview`
- **Get the App** → `/platforms`

---

### `quickstart.mdx`

**Title:** Quickstart  
**Description:** Get your first event planned in under 5 minutes  

Write a step-by-step quickstart guide with these steps:

1. **Sign up or log in** — Go to app.fastparty.ai or download the iOS/Android app. Create a free account with your email.
2. **Create your first event** — Click "New Event", give it a name, set a date and time, add a location, and set an expected guest count.
3. **Invite your guests** — Add guest names and emails. FastParty sends invitations automatically.
4. **Set up your agenda** — Add activities with start times and durations, then publish so guests can see the plan.
5. **Configure food preferences** — Set dietary options and enable guests to select their preferences before the event.
6. **Assign tasks** — Create a pre-event checklist with due dates to stay on top of your planning.
7. **Try Antsy, your AI concierge** — Open the Antsy chat inside FastParty and describe what you need. Antsy can do all of the above for you through conversation.

Include a `<Tip>` block: "Already a Claude user? You can do all of this directly inside Claude without opening the FastParty app. See the [Claude Integration](/claude-integration/overview) guide."

---

### `platforms.mdx`

**Title:** Platforms & Apps  
**Description:** FastParty is available on iOS, Android, and web  

Cover:
- **Web app** at app.fastparty.ai — works in any modern browser, no install required
- **iOS app** — available on the App Store (link placeholder: `https://apps.apple.com/app/fastparty`)
- **Android app** — available on Google Play (link placeholder: `https://play.google.com/store/apps/fastparty`)
- **Claude AI** — FastParty works inside Claude via the Connector Store (no app needed, see Claude Integration section)

Note that all platforms are kept in sync — events created on one device appear instantly on all others.

---

## 5. Feature Pages

---

### `features/events.mdx`

**Title:** Events  
**Description:** Create and manage your events  
**Icon:** `calendar`

Cover the following in full detail:

**Creating an Event**
- Fields: Event name, Date, Start time, Location (optional), Expected guest count, Event description (optional), Cover image (optional)
- Events can be created manually via the app or by talking to Antsy ("Create a birthday party for Saturday at 7 PM with 20 guests")

**Event Status**
- Draft — being set up, not yet shared with guests
- Confirmed — live, invitations can be sent
- Cancelled — guests are notified

**Editing an Event**
- All fields can be edited at any time from the event settings page
- Changes to date/time prompt an optional notification to already-invited guests

**Viewing Your Events**
- Dashboard shows upcoming events sorted by date
- Past events are archived and accessible from the event history

**Deleting an Event**
- Events can be deleted from event settings
- Guests with pending invitations are notified

Include a `<Note>` block: "FastParty is designed for personal and social events — birthday parties, dinner parties, potlucks, holiday gatherings, work team events, and more."

---

### `features/guests.mdx`

**Title:** Guests & RSVPs  
**Description:** Invite guests and track responses  
**Icon:** `users`

Cover:

**Adding Guests**
- Add guests individually by name and email
- Add multiple guests at once (bulk entry)
- Import from a CSV file
- Add from a saved Circle (guest group)

**Sending Invitations**
- Invitations are sent by email automatically when a guest is added (or on demand)
- Invitation email includes event name, date, time, location, and RSVP link
- Guests do not need a FastParty account to RSVP

**RSVP Tracking**
- Status options: Pending, Accepted, Declined, Maybe
- Dashboard shows a real-time RSVP count
- Filter guests by RSVP status
- Send reminder to guests who haven't responded

**Guest Details**
- Name, email, RSVP status, dietary preference (if configured), potluck contribution (if configured)

**Removing Guests**
- Guests can be removed from an event at any time
- Removed guests are notified by email

Include a `<Tip>` block: "Use Circles to save groups of guests you invite regularly — family, work team, book club — so you can add everyone in one click for future events."

---

### `features/agenda.mdx`

**Title:** Agenda & Schedule  
**Description:** Plan your event timeline and share it with guests  
**Icon:** `list-check`

Cover:

**Creating Agenda Activities**
- Add activities with: Title, Start time, Duration, Description (optional), Location/room (optional)
- Activities are ordered automatically by start time
- Overlapping times are flagged with a warning

**Publishing the Agenda**
- Agenda is private until published
- Once published, invited guests can view the timeline via their invitation link
- Updates to a published agenda are reflected in real time for guests

**Unpublishing**
- Agenda can be unpublished at any time (guests lose access to the timeline view)

**Example agendas** — show three brief examples:
- Birthday party timeline
- Work team lunch timeline  
- Potluck dinner timeline

---

### `features/food-and-beverage.mdx`

**Title:** Food & Beverage Preferences  
**Description:** Collect dietary preferences from your guests before the event  
**Icon:** `utensils`

Cover:

**Setting Up Preferences**
- Create a list of dietary options relevant to your event (e.g. Vegetarian, Vegan, Gluten-Free, Nut Allergy, Halal, Kosher, Dairy-Free, No Restrictions)
- Custom options can be added for any event

**Enabling Guest Responses**
- Preferences are hidden from guests until you publish/enable them
- Once enabled, guests see the options on their RSVP/invitation page and can select what applies to them

**Viewing Responses**
- See a summary of how many guests selected each option
- View individual guest selections
- Export the list for caterers or food planning

Include a `<Note>` block: "Food preference data is shown only to the event organiser. Guests only see the options, not each other's selections."

---

### `features/potluck.mdx`

**Title:** Potluck  
**Description:** Organise potluck contributions with sign-up sheets  
**Icon:** `bowl-food`

Cover:

**Creating a Potluck**
- Define categories (e.g. Main Dishes, Salads, Desserts, Drinks, Sides)
- Set how many items are needed per category
- Set portion size guidance per category (optional, e.g. "serves 6")

**Publishing the Potluck**
- Potluck sign-up is hidden until published
- Once published, guests see the categories and available slots on their invitation page
- Guests can claim a slot and enter what they plan to bring

**Tracking Contributions**
- Dashboard shows which slots are filled and which are still open
- See each guest's contribution
- Send a reminder to guests who haven't signed up

**Editing After Publishing**
- Categories and slot counts can be adjusted after publishing
- Guests who already signed up are not affected unless their slot is removed

---

### `features/tasks.mdx`

**Title:** Tasks  
**Description:** Create a pre-event checklist to stay on track  
**Icon:** `square-check`

Cover:

**Creating Tasks**
- Fields: Task title, Due date, Assigned to (optional — organiser or a team member by email), Notes (optional)
- Tasks can be created in bulk by describing them to Antsy

**Task Status**
- Open — not yet done
- In Progress — being worked on
- Complete — done

**Assigning Tasks**
- Tasks can be assigned to yourself or any collaborator/co-organiser on the event
- Assigned team members receive an email notification

**Tracking Progress**
- Tasks view shows all tasks sorted by due date
- Filter by status or assignee
- Overdue tasks are highlighted

---

### `features/circles.mdx`

**Title:** Circles  
**Description:** Save guest groups to speed up future event planning  
**Icon:** `circle-nodes`

Cover:

**What Is a Circle?**
- A Circle is a saved group of guests with a name (e.g. "Family", "Work Team", "Book Club", "Neighbours")
- Once created, a Circle can be added to any future event with a single action, adding all members instantly

**Creating a Circle**
- Give the Circle a name
- Add members by name and email
- Members can be added or removed from a Circle at any time without affecting past events

**Using a Circle in an Event**
- When adding guests to an event, select "Add from Circle"
- All Circle members are added at once
- Individual members can be removed from the event after adding if needed

**Managing Circles**
- View all Circles from your account settings
- Edit member lists, rename, or delete Circles

Include a `<Tip>` block: "Circles are perfect for recurring events — annual family dinners, monthly team lunches, or seasonal gatherings. Set up your Circles once and every future event setup takes seconds."

---

### `features/antsy-ai.mdx`

**Title:** Antsy — Your AI Event Concierge  
**Description:** Plan your entire event through conversation  
**Icon:** `wand-magic-sparkles`

Cover:

**What Is Antsy?**
- Antsy is FastParty's built-in AI concierge, available inside the app on iOS, Android, and web
- Users can describe what they need in plain language and Antsy handles the setup — no menus, no forms
- Antsy is powered by AI and understands natural, conversational requests

**What Antsy Can Do**
Write out each capability with a short example prompt:
- Create events: *"Plan a housewarming party for next Saturday at 6 PM, around 40 guests"*
- Add guests and send invitations: *"Add my friend Sarah (sarah@email.com) and send her an invite"*
- Build agendas: *"Set up a timeline — cocktails at 6, dinner at 7:30, dessert at 9"*
- Configure food preferences: *"Set up vegetarian and vegan options and enable them for guests"*
- Organise potlucks: *"Create a potluck with mains, sides, and desserts — 3 of each"*
- Create tasks: *"Remind me to book the caterer by the 10th and order flowers by the 12th"*
- Answer questions about your event: *"How many people have RSVP'd so far?"*

**How to Use Antsy**
- Open the Antsy chat from the bottom tab bar in the mobile app, or the chat icon in the web app
- Type or speak your request
- Antsy confirms what it has done and shows the results inline
- You can refine or make changes: *"Actually, move dinner to 8 PM"*

Include a `<Note>` block: "Antsy remembers the context of your conversation within a session — you can refer back to 'the event I just created' or 'the guests I added earlier' without repeating details."

---

## 6. Claude Integration Pages

---

### `claude-integration/overview.mdx`

**Title:** FastParty in Claude  
**Description:** Manage your events directly from Claude AI  
**Icon:** `robot`

Cover:

**What Is This?**
- FastParty is available as an official connector in the Claude Connector Store
- Once connected, users can manage their entire FastParty account through conversation with Claude — no need to open the FastParty app
- The integration uses FastParty's MCP (Model Context Protocol) server, hosted at `mcp.fastparty.ai`

**Who Is This For?**
- Existing FastParty users who also use Claude and want a seamless, single-interface experience
- Power users who prefer doing everything through AI conversation
- Teams using Claude for productivity who want event planning built in

**How It Compares to Antsy**

Use a comparison table:

| | Antsy (in FastParty app) | FastParty in Claude |
|---|---|---|
| Where you access it | FastParty app (iOS, Android, web) | Claude (claude.ai or Claude app) |
| Requires FastParty app | Yes | No |
| Requires Claude account | No | Yes |
| Best for | App-first users | Claude-first users |
| Capabilities | Full FastParty feature set | Full FastParty feature set |

Include a `<Card>` linking to the connect guide: "Ready to connect? → /claude-integration/connect"

---

### `claude-integration/connect.mdx`

**Title:** Connecting FastParty to Claude  
**Description:** Add FastParty to Claude in a few clicks  
**Icon:** `plug`

Write a clear, non-technical step-by-step connection guide:

**Steps:**
1. Open Claude at claude.ai or in the Claude app
2. Click the connector/plug icon or navigate to Settings → Connectors
3. Search for "FastParty" in the Connector Store
4. Click Connect on the FastParty listing
5. A FastParty sign-in window will appear — log in with your FastParty account credentials
6. Review the permissions FastParty is requesting and click Authorize
7. You'll be returned to Claude. FastParty is now connected.
8. Test it: ask Claude "What FastParty tools do you have access to?"

**What Permissions Are Requested?**
List in plain English (not scope names):
- Create and update your events
- Add guests and send invitations
- View RSVP statuses
- Set up agendas, tasks, food preferences, and potlucks
- Create guest circles

**Disconnecting**
- Go to Claude Settings → Connectors → FastParty → Disconnect
- Your FastParty data is never affected by disconnecting

Include a `<Note>` block: "FastParty in Claude requires a Claude Pro account or higher. The connection is per user — each team member connects their own FastParty account."

---

### `claude-integration/what-you-can-do.mdx`

**Title:** What You Can Do in Claude  
**Description:** Full list of FastParty actions available through Claude  
**Icon:** `list`

Write a full feature-by-feature breakdown of what Claude can do with FastParty. For each feature, include a short plain-English description and 1–2 example prompts. Features to cover:

- Create events
- Update event details
- Add guests and send invitations
- Check RSVP status
- Build and publish event agendas
- Configure and publish food & dietary preferences
- Create and publish potluck sign-ups
- Create and assign tasks
- Create guest circles

End with a `<Tip>` block: "You can chain actions in a single message — 'Create a birthday party for July 5th, add these three guests, and set up a vegetarian and vegan preference option' — and Claude will handle all of it in sequence."

---

### `claude-integration/example-prompts.mdx`

**Title:** Example Prompts  
**Description:** Ready-to-use prompts for managing FastParty through Claude  
**Icon:** `message`

Organise prompts by category using `<AccordionGroup>` and `<Accordion>` components. Categories and prompts:

**Events**
- "Create a birthday dinner for my daughter on July 5th at 7 PM. We're expecting 20 guests at our house."
- "Update my July 5th party — change the start time to 7:30 PM."
- "What events do I have coming up in the next two weeks?"
- "Cancel my August 10th event and notify guests."

**Guests & RSVPs**
- "Add Sarah Johnson (sarah@email.com) and Mark Lee (mark@email.com) to my July 5th party and send them invitations."
- "How many people have RSVP'd to my party so far?"
- "Who hasn't responded to the invitation yet?"
- "Send a reminder to everyone who hasn't RSVP'd."
- "Remove David Brown from the guest list."

**Agenda**
- "Set up an agenda for my July 5th event: Welcome drinks at 7:30 PM for 30 minutes, dinner at 8 PM for 90 minutes, cake at 9:30 PM. Then publish it."
- "Add a 'Group photo' activity at 9 PM for 15 minutes to my party agenda."
- "What does the current agenda for my July 5th event look like?"

**Food & Dietary Preferences**
- "Set up vegetarian, vegan, gluten-free, and nut-allergy options for my event and enable guests to select them."
- "Which guests have selected vegetarian for my July 5th party?"

**Potluck**
- "Create a potluck for my July 5th event with: Main Dishes (3 needed), Salads (2 needed), Desserts (3 needed), and Drinks (2 needed). Then publish it."
- "How many potluck slots are still unfilled?"

**Tasks**
- "Create these tasks for my July 5th event: confirm headcount by June 28, order cake by July 1, buy decorations by July 3."
- "Mark the 'order cake' task as complete."
- "What tasks are still open for my July 5th event?"

**Circles**
- "Create a circle called 'Family' and add these people: [list of names and emails]."
- "Add everyone from my 'Work Team' circle to my August event."

---

### `claude-integration/faq.mdx`

**Title:** Claude Integration FAQ  
**Description:** Common questions about using FastParty in Claude  
**Icon:** `circle-question`

Use `<AccordionGroup>` and `<Accordion>` for each question. Cover:

- Do I need to install anything?
- Is my FastParty password shared with Claude?
- What happens if I disconnect FastParty from Claude?
- Does this work on the Claude mobile app?
- What Claude plan do I need?
- What if Claude says it can't access FastParty?
- Can multiple team members connect their own accounts?
- Is the connection always active or do I need to reconnect?
- Can Claude delete my events or data?
- Where is my data stored?

For each, write a clear, reassuring, non-technical answer (2–4 sentences).

---

## 7. Account Pages

---

### `account/profile.mdx`

**Title:** Your Profile  
**Description:** Manage your name, email, and account details  

Cover: updating display name, email address, profile photo, and timezone. Note that email changes require re-verification.

---

### `account/notifications.mdx`

**Title:** Notifications  
**Description:** Control how FastParty communicates with you  

Cover: email notifications for event updates, RSVP responses, task reminders, and potluck sign-ups. Explain how to turn each on or off.

---

### `account/billing.mdx`

**Title:** Billing & Plans  
**Description:** Manage your FastParty subscription  

Cover:
- Free plan: what's included (basic events, limited guests per event)
- Paid plans: mention that details are available at fastparty.ai/pricing
- How to upgrade, downgrade, or cancel
- Where to find invoices
- Note: "For billing questions, email support@fastparty.ai"

---

### `account/security.mdx`

**Title:** Security  
**Description:** Keep your FastParty account secure  

Cover:
- Changing your password
- Logging out of all devices
- Viewing connected apps (including Claude integration)
- Revoking app access
- Contact support if you suspect unauthorized access

---

## 8. Troubleshooting Pages

---

### `troubleshooting/common-issues.mdx`

**Title:** Common Issues  
**Description:** Solutions to the most frequently reported problems  

Use `<AccordionGroup>` for each issue. Cover these issues with clear resolution steps:

**App & Account**
- Can't log in / forgot password
- Not receiving invitation emails (check spam, verify email address)
- App not loading on mobile

**Events & Guests**
- Guest didn't receive invitation
- RSVP link not working for a guest
- Can't edit an event after publishing

**Antsy (AI Concierge)**
- Antsy isn't responding
- Antsy did something wrong / made an error
- Antsy created the wrong event details

**Claude Integration**
- FastParty doesn't appear in the Claude Connector Store
- OAuth sign-in fails when connecting to Claude
- Claude says it can't access FastParty (401 error)
- FastParty tools don't appear after connecting
- Actions in Claude aren't reflecting in the FastParty app

---

### `troubleshooting/contact-support.mdx`

**Title:** Contact Support  
**Description:** Get help from the FastParty team  

Cover:
- Email support: support@fastparty.ai — response within 1 business day
- Help center: help.fastparty.ai
- In-app help: tap the help icon in the FastParty app to start a chat
- When contacting support, include: account email, device/platform, steps to reproduce the issue, any error messages seen

Use a `<Card>` component for each support channel.

---

## 9. Writing Style Guide for Claude Code

Follow these guidelines when writing the MDX content:

**Tone**
- Friendly, clear, and encouraging — not technical or corporate
- Write for a non-technical user who is excited to plan events
- Use "you" throughout (second person)
- Short sentences. Active voice.

**Formatting rules**
- Use `<Note>` for important information the user should be aware of
- Use `<Tip>` for helpful shortcuts or best practices
- Use `<Warning>` sparingly, only for potentially irreversible actions
- Use `<CardGroup>` and `<Card>` for navigation and feature overviews
- Use `<AccordionGroup>` and `<Accordion>` for FAQs and troubleshooting
- Use `<Steps>` for sequential how-to instructions
- Code blocks (` ``` `) for any prompts or example messages to Claude
- Tables for comparisons

**Frontmatter for every page**
```
---
title: "Page Title"
description: "One sentence description under 160 characters"
---
```

**Never use:**
- Jargon like "MCP", "OAuth", "Bearer token", "HTTP", "API" in customer-facing pages (these terms are fine in the Claude Integration technical section only)
- Passive voice
- More than 3 bullet points in a row without a heading break
- Walls of text — break content into sections with h2/h3 headings

---

## 10. Additional Notes for Claude Code

1. Create all files listed in section 3. Do not skip any.
2. The `mint.json` should be created exactly as specified in section 2.
3. All internal links should use relative paths (e.g. `/features/events`, `/claude-integration/overview`).
4. Use Mintlify's built-in components (`<Card>`, `<CardGroup>`, `<Note>`, `<Tip>`, `<Warning>`, `<Steps>`, `<AccordionGroup>`, `<Accordion>`, `<Tabs>`, `<Tab>`) — do not use raw HTML.
5. Every page must have a complete frontmatter block with `title` and `description`.
6. The Claude Integration section should be thorough but non-technical for the FAQ and connect pages. The `overview.mdx` may mention MCP briefly with a one-line plain-English explanation.
7. Placeholder image paths like `/images/screenshot-events.png` can be added where screenshots would improve comprehension — label them clearly so they can be swapped with real screenshots later.
8. After creating all files, output a summary of every file created and its path.