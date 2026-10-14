# ✉️ LinkedIn to Email (No Cookies) ✅ Bulk

Turn LinkedIn person profile URLs into email addresses at scale. Add a list of LinkedIn profile URLs, run the Actor, and receive clean results that can be exported or sent directly to your CRM, spreadsheet, outreach platform, or automation workflow.

No LinkedIn cookies, login, or active LinkedIn session required.

---

## 👥 Who Is LinkedIn to Email For?

LinkedIn to Email is designed for teams and operators who need email enrichment from LinkedIn profile URLs without connecting their own LinkedIn accounts.

- Sales and growth teams building outbound prospect lists
- Recruiters and talent sourcers enriching candidate records
- Founders and operators improving lead and contact databases
- Analysts and researchers connecting professional profiles with contact data
- Automation teams building workflows in n8n, Make, Zapier, or custom applications

---

## 🔍 What Does This Actor Do?

The Actor processes LinkedIn person profile URLs and attempts to return one email address for each URL.

- Accepts LinkedIn person profile URLs in bulk
- Finds one email address per profile when available
- Returns structured data that is easy to export or process
- Supports thousands of URLs in a single workflow
- Works without your LinkedIn cookies or session

---

## 💡 Main Advantages

- **Simple output:** Receive only the fields needed for matching and enrichment
- **Bulk processing:** Enrich large LinkedIn profile lists in one run
- **No-cookie workflow:** No LinkedIn login cookies are required
- **No account connection:** Your LinkedIn account is not used to run the enrichment
- **Automation-ready:** Use the output in APIs, webhooks, CRMs, spreadsheets, and automation tools

---

## ⚙️ Input

Provide a tag name and a list of LinkedIn person profile URLs.

| Input | Required | Description |
|---|---|---|
| `fileName` | Yes | A label/tag for this run, used to identify the batch |
| `profiles` | Yes | Array of LinkedIn person profile URLs to enrich |

### Sample Input

```json
{
  "fileName": "test",
  "profiles": [
    "http://www.linkedin.com/in/craig-rossi-7388259"
  ]
}
```

---

## 📌 Output Fields

| Field | Description |
|---|---|
| `ordinal` | Row number within the batch |
| `input_url` | LinkedIn URL as submitted in the input |
| `linkedin_url` | Normalized LinkedIn profile URL |
| `status` | Processing status (`success` or `failed`) |
| `stage` | Stage at which processing stopped (e.g. `domain`, `email`) |
| `first_name` | First name from the LinkedIn profile |
| `last_name` | Last name from the LinkedIn profile |
| `company_name` | Current employer name |
| `company_url` | Current employer website URL |
| `domain` | Domain used for email pattern matching |
| `domain_source` | Source used to find the domain |
| `email` | Email address found for the profile |
| `email_status` | Verification status of the email |
| `profile_source` | Data source used to fetch the profile |
| `error` | Reason for failure if status is `failed` |
| `waiting_reason` | Reason the record is queued, if applicable |
| `duplicate_of` | Input URL this record is a duplicate of, if applicable |
| `request_id` | Unique identifier for this enrichment request |
| `updated_at` | Timestamp of when the record was last updated |

If no email is available for a profile, the `email` field will be empty.

---

## 📊 Sample Output

```json
{
  "ordinal": "1",
  "input_url": "http://www.linkedin.com/in/craig-rossi-7388259",
  "linkedin_url": "https://www.linkedin.com/in/craig-rossi-7388259",
  "status": "failed",
  "stage": "domain",
  "first_name": "Craig",
  "last_name": "Rossi",
  "company_name": "",
  "company_url": "",
  "domain": "",
  "domain_source": "",
  "email": "",
  "email_status": "",
  "profile_source": "brightdata",
  "error": "Current employer website could not be verified; a company website is needed",
  "waiting_reason": "",
  "duplicate_of": "",
  "request_id": "bb6547f9-7317-4f6d-bd2a-2b55b03c9dac",
  "updated_at": "2026-10-14T06:22:42.365627+00:00"
}
```

The example demonstrates the output structure and does not guarantee that the displayed email is currently available or valid.

---

## 🧠 Common Use Cases

- **Lead generation:** Find emails for prospects collected from LinkedIn
- **Outbound sales:** Prepare enriched contact lists for campaigns
- **Recruitment:** Find candidate email addresses for direct outreach
- **CRM enrichment:** Add email fields to existing LinkedIn-based records
- **Data pipelines:** Use the Actor as an email-enrichment step
- **Automation workflows:** Connect it with n8n, Make, Zapier, or custom scripts

---

## 📁 How to Use

1. Create or sign in to your Apify account.
2. Open the LinkedIn to Email Actor.
3. Add your `fileName` tag and LinkedIn person profile URLs.
4. Run the Actor.
5. Review the results in the dataset.
6. Download the output or connect it to your workflow through the Apify API.

---

## ⚠️ Data Availability

Email availability varies by person and the data sources available at the time of the run. The Actor may not find an email for every LinkedIn URL. An empty `email` field means no email was available for that input during processing.

Use the returned data responsibly and follow applicable privacy, data-protection, anti-spam, and outreach regulations.
