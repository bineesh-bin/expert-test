## Lead Capture Form - Saving Leads to Supabase

The lead capture form in this project now saves lead data directly to the Supabase database when the form is submitted. This includes the lead's name, email, industry, and submission timestamp.

### How it works

- On form submission, the input data is validated.
- If valid, the lead data is inserted into the `leads` table in Supabase.
- A confirmation email is sent via a Supabase Edge Function.
- The form resets and shows a success message.

### Fixes and Code Changes

Two key fixes were made in the lead capture form:

1. **Saving Leads to Supabase Database:**
   - Added code to insert lead data into the `leads` table in Supabase.
   - This ensures leads are persisted in the database on form submission.
   - Errors during insertion are logged and prevent further processing.

2. **Removed Duplicate Confirmation Email Function Call:**
   - Previously, the `send-confirmation` Supabase function was called twice.
   - The duplicate call was removed to avoid redundant email sends.
   - Now, the confirmation email function is invoked only once after saving the lead.

### Supabase Setup

Ensure your Supabase project has a `leads` table with the following columns:

- `id` (UUID or serial primary key)
- `name` (text)
- `email` (text)
- `industry` (text)
- `submitted_at` (timestamp)

### Notes

- Errors during saving or email sending are logged to the console.
- You can customize the table name or fields in `LeadCaptureForm.tsx` as needed.






# Welcome to your Lovable project

## Project info

**URL**: https://lovable.dev/projects/94b52f1d-10a5-4e88-9a9c-5c12cf45d83a

## How can I edit this code?

There are several ways of editing your application.

**Use Lovable**

Simply visit the [Lovable Project](https://lovable.dev/projects/94b52f1d-10a5-4e88-9a9c-5c12cf45d83a) and start prompting.

Changes made via Lovable will be committed automatically to this repo.

**Use your preferred IDE**

If you want to work locally using your own IDE, you can clone this repo and push changes. Pushed changes will also be reflected in Lovable.

The only requirement is having Node.js & npm installed - [install with nvm](https://github.com/nvm-sh/nvm#installing-and-updating)

Follow these steps:

```sh
# Step 1: Clone the repository using the project's Git URL.
git clone <YOUR_GIT_URL>

# Step 2: Navigate to the project directory.
cd <YOUR_PROJECT_NAME>

# Step 3: Install the necessary dependencies.
npm i

# Step 4: Start the development server with auto-reloading and an instant preview.
npm run dev
```

**Edit a file directly in GitHub**

- Navigate to the desired file(s).
- Click the "Edit" button (pencil icon) at the top right of the file view.
- Make your changes and commit the changes.

**Use GitHub Codespaces**

- Navigate to the main page of your repository.
- Click on the "Code" button (green button) near the top right.
- Select the "Codespaces" tab.
- Click on "New codespace" to launch a new Codespace environment.
- Edit files directly within the Codespace and commit and push your changes once you're done.

## What technologies are used for this project?

This project is built with:

- Vite
- TypeScript
- React
- shadcn-ui
- Tailwind CSS

## How can I deploy this project?

Simply open [Lovable](https://lovable.dev/projects/94b52f1d-10a5-4e88-9a9c-5c12cf45d83a) and click on Share -> Publish.

## Can I connect a custom domain to my Lovable project?

Yes, you can!

To connect a domain, navigate to Project > Settings > Domains and click Connect Domain.

Read more here: [Setting up a custom domain](https://docs.lovable.dev/tips-tricks/custom-domain#step-by-step-guide)
