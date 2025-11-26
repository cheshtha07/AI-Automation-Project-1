# 📍AI Automation Project-1 : Automating CSV Append from Email to Postgres DB.

## Overview
This project is about 𝐫𝐞𝐦𝐨𝐯𝐢𝐧𝐠 𝐦𝐚𝐧𝐮𝐚𝐥 𝐞𝐟𝐟𝐨𝐫𝐭 from a common workflow: updating a database whenever new CSV files arrive via email. Instead of downloading attachments and uploading them manually, I used 𝐧𝟖𝐧 (𝐚𝐧 𝐚𝐮𝐭𝐨𝐦𝐚𝐭𝐢𝐨𝐧 𝐭𝐨𝐨𝐥) to build a pipeline that does it automatically.

## Tools
1. **n8n** - It is a workflow automation software,to automate CSV data updates to a Postgres database.
2. **ChatGPT/Perplexity** - To help with the automation process. 
3. **Supabase** - For creating a Postgres database and Node.js for setting up n8n locally.


## Here’s how the workflow works

1️⃣ 𝐒𝐞𝐭 𝐮𝐩 𝐧𝟖𝐧 𝐚𝐜𝐜𝐨𝐮𝐧𝐭
- Created an automation workspace where workflows can be designed visually.
  
2️⃣ 𝐂𝐨𝐧𝐟𝐢𝐠𝐮𝐫𝐞 𝐆𝐦𝐚𝐢𝐥 𝐄𝐦𝐚𝐢𝐥‑𝐖𝐚𝐭𝐜𝐡𝐞𝐫 𝐍𝐨𝐝𝐞
- Connected my Gmail account to n8n.
- Enabled attachment capture so the workflow detects incoming emails with CSV files.

3️⃣ 𝐑𝐞𝐭𝐫𝐢𝐞𝐯𝐞 𝐂𝐨𝐧𝐭𝐞𝐧𝐭 𝐚𝐧𝐝 𝐀𝐭𝐭𝐚𝐜𝐡𝐦𝐞𝐧𝐭𝐬
- Pulled in each new email’s subject, body, and attached files.
- Ensured the workflow only processes relevant emails.

4️⃣ 𝐓𝐮𝐫𝐧 𝐂𝐒𝐕𝐬 𝐢𝐧𝐭𝐨 𝐑𝐨𝐰𝐬
- Used a CSV‑Parse node to convert the binary file into structured JSON rows.
- The first row of the CSV was treated as headers to map data correctly.

5️⃣ 𝐋𝐨𝐚𝐝 𝐃𝐚𝐭𝐚 𝐢𝐧𝐭𝐨 𝐏𝐨𝐬𝐭𝐠𝐫𝐞𝐬
- Connected n8n to my Postgres database.
- Mapped each CSV column to its matching table column.
- Inserted rows automatically into the database.

6️⃣ 𝐓𝐞𝐬𝐭, 𝐓𝐰𝐞𝐚𝐤, 𝐚𝐧𝐝 𝐆𝐨 𝐋𝐢𝐯𝐞
- Sent myself a sample CSV to test the workflow.
- Verified that new rows appeared in Postgres.
- Activated the workflow and monitored the first few runs for reliability.

## Key Insights
1. This process includes setting up a Gmail trigger, filtering emails, extracting data, and mapping fields.
2. This project also taught me instead of repetitive manual uploads, the system now ensures real‑time updates to the database with minimal human intervention.
3. It’s a small but powerful step toward AI‑driven automation in data pipelines.

