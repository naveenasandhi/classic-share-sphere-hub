# ShareSphere - Testing Instructions for Judges

**Live application:** https://classic-share-sphere-hub.base44.app

ShareSphere is a shared-resource platform where verified users discover equipment, request bookings, join fair waiting lists and report incidents, while owners, managers and administrators oversee access. This guide lists only the features available in the published demo.

## 1. Before You Start

- Use a desktop browser (Chrome, Edge or Firefox). Allow about 10-15 minutes.
- The app runs in a **Demo Workspace** (badge shown at the top left). All organisations, people, documents, bookings and incidents are **fictional**. Do not enter real personal data.
- **Login credentials:** dedicated test-account details are provided separately through the submission method approved by the organizers. No passwords or secret keys are published in this repository.
- After signing in, use the **"View as"** dropdown in the top bar to switch between the **User**, **Owner**, **Manager** and **Administrator** views without logging out.

## 2. Quick Path (3 minutes)

1. Open the application and read the landing page.
2. Sign in with the test account.
3. Open **Discover** and browse the catalogue.
4. Open **My dashboard** and **Waiting list**.
5. Switch to **Manager** and open **Manager console**.
6. Open **Audit trail** and confirm your actions were recorded.

## 3. Detailed Test Steps

### Step 1 - Open the application
1. Go to the live URL above.
2. **Expected:** The landing page shows "Access More. Waste Less.", an example booking record, and **Sign in**, **Create account** and **Enter the platform** buttons. The page lists 4 enforced roles, 4 verification states and 9 resource categories.

### Step 2 - Sign in
1. Click **Sign in** (or **Enter the platform**) and use the test account supplied by the organizers.
2. **Expected:** You land in the app with a left navigation menu (Discover, My dashboard, Waiting list, Incidents, Notifications, plus Sharing and Account sections) and the Demo Workspace badge.

### Step 3 - Browse available resources
1. Click **Discover**.
2. Scroll the catalogue: **12 resources** are listed with photos, location, availability status, price per booking, deposit and maximum duration.
3. Use the category chips (Laboratory, Classroom, Meeting Room, Computer, Camera, Fabrication Tool, Testing Device, Workshop Equipment, Other) and the search box (for example type "laser" or "microscope").
4. Check the requirement badges on cards: **Training required**, **Supervised**, **Verified members**.
5. **Expected:** The list filters as you search or pick a category; each listing states its eligibility rules before you request it.

### Step 4 - Try Smart match
1. On Discover, find the **Smart match** panel.
2. Describe a purpose (for example "imaging cells" or "cutting plywood") and optionally a budget.
3. **Expected:** The catalogue is ranked using deterministic rules (keyword overlap, cost, availability, and whether your recorded training and verification satisfy the listing). It does not use an AI model and never assumes you are qualified.

### Step 5 - Review your dashboard and booking status
1. Click **My dashboard**.
2. **Expected:** Summary cards show Upcoming, Awaiting decision, In your hands and Waiting list counts. Below them you will see:
   - **Upcoming bookings** with an **Approved** status (for example Epilog Zing 16 Laser Cutter and Sony A7 III Camera Kit).
   - **Pending requests** with a **Pending Review** status (for example Prusa MK3S+ 3D Printer).
   - An **overdue booking alert** with an **Open booking** button.
   - **Recent activity** notifications.
3. Click **Open booking** (or any booking) to view the booking detail and its status.

### Step 6 - Submit a booking request
1. From **Discover**, open a resource that shows **Available** and choose the option to request a booking.
2. Select a date and time slot and submit the request.
3. Return to **My dashboard**.
4. **Expected:** The new request appears under **Pending requests** with a **Pending Review** status until the resource owner or a manager decides. The request is subject to the fair-use limits set by the administrator.

### Step 7 - Check the waiting list
1. Click **Waiting list**.
2. **Expected:** The page explains how the queue works (explainable priority, first in line is offered first, no automatic penalties). "Your entries" shows the Zeiss LSM 880 Confocal Microscope entry at position **#1** with status **Waiting** and the recorded priority factors (verified member +15, no recent use +20, owner policy: course work first). The table "Queues across your resources" lists the same entry.

### Step 8 - Test incident reporting
1. Click **Incidents**.
2. Review the existing reports (Scheduling conflict - Under Review, Damage - Submitted, Late return - Resolved with an outcome).
3. In the **Report a new issue** form, choose a related resource (or "Not linked to a specific resource"), a category (for example Damage), a severity (for example medium), and describe what happened.
4. Click **Submit report**.
5. **Expected:** The new report appears in the list in a **Submitted** state. The page states that a report never charges a deposit or suspends an account on its own; a person must review the evidence first.

### Step 9 - Test manager functions
1. In the top bar, set **View as** to **Manager** (or use a manager account).
2. Open **Manager console**.
3. **Expected:** The console shows the Verification queue, Open incidents, Waiting list and High-demand counts.
4. **Verification queue:** type a note in "Reviewer notes", then click **Approve** or **Reject** on the pending request (the fictional applicant "Rahul Verma", student ID document). The applicant's status changes and a notification is created.
5. **Incident oversight:** click **Review as manager** on an incident from the Incidents page, then record a decision and outcome.
6. The console also has a **Record a training completion** form, which records the training that unlocks equipment requiring it.

### Step 10 - Test administrator functions
1. Set **View as** to **Administrator**.
2. Open **Administration**.
3. **Expected:** Platform totals are shown (people, resources, bookings, incidents). The **People & roles** table lists each person's organisation, roles and verification status. The **Fair-use limits** panel shows Active bookings per user (5), Requests per 30 days (10), High-demand threshold (4), a **Demo mode** checkbox and a **Maintenance notice** field.
4. Change a value (for example the high-demand threshold) and save it, then confirm that the Manager console "High-demand" figure and booking limits reflect the change.

### Step 11 - Check the audit trail
1. Open **Audit trail**.
2. **Expected:** An append-only list shows when, who (actor and role), the action (for example `booking.approved`, `incident.submitted`, `verification.approved`), the related record, details and the reason. Use the record-type filter and the search box (for example "Naveena" or "laser").
3. Entries cannot be edited or deleted by ordinary users.

### Step 12 - Other pages (optional)
- **Notifications:** shows alerts such as an approval, an overdue return or a slot offered.
- **Profile & verification:** shows your verification state and the evidence you submitted.
- **Help & guidelines** and **Project docs:** explain how the platform works.
- **Owner studio:** where owners manage their listings and decide on booking requests.

## 4. What Is Not Included

To set expectations, the following are **not** part of this demo: real payment or deposit processing, email/SMS notifications (alerts are in-app only), automated identity or document verification, and training content or quizzes. Photos and all records are illustrative demo data.

## 5. Troubleshooting

| Problem | What to try |
|---|---|
| Page does not load | Refresh, or open the URL in a private window. |
| Sign-in is rejected | Re-check the credentials from the organizers; use the Google/email option exactly as instructed. |
| A menu item is missing (for example Manager console) | Use the **View as** dropdown to switch role; some screens are role-specific. |
| The demo data looks changed after earlier tests | Dates and statuses may change after other judges' actions; the workflow still behaves as described. |

## 6. Contact

Naveena Sandhi - Team Member 1 / Developer
