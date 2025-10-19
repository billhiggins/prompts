# Prompt: Generate Team-Member Podcast Summary from RSS Feed

Use this prompt to regenerate an updated Markdown list of **Mixture of Experts** podcast episodes featuring team members.  
The goal is to produce the results directly in ChatGPT for easy copy-paste into Slack or documents.

- Tested and verified with ChatGPT (GPT-5, October 2025 release) — results and formatting confirmed accurate for this model.

---

## Step 1 — Get the RSS Feed

1. Visit the official *Mixture of Experts* RSS feed:  
   👉 **https://feeds.casted.us/95/Mixture-of-Experts-0d38e236/feed**  
2. Right-click → **Save As…** → choose “Web Page, XML” or “Feed” and save the file as  
   `MOE_RSS_<today’s date>.xml`.  
3. Upload that file into this ChatGPT session.

---

## Step 2 — Run This Prompt

Paste everything below into ChatGPT after uploading the file:

---

### PROMPT START

You are to analyze the uploaded *Mixture of Experts* RSS XML file and generate a Markdown summary of all episodes featuring the following team members:

**Team members:** Gabe Goodhart, Lauren McHugh, Olivia Buzek

**Instructions:**

1. **Parse the RSS feed** completely for all `<item>` entries.  
2. Extract from each episode:
   - Title  
   - Publication date (`<pubDate>`)  
   - Link (`<link>`)  
   - Full text of the description (`<description>`)

3. **Identify appearances** by any of the listed team members by checking both the title and description text.  
   - Include an episode if a team member’s name appears in either.  

4. **Extract guest names:**  
   - Detect full human names (two or more capitalized words) in the description.  
   - Typical cues: “host … is joined by …”, “joined by …”, “featuring …”.  
   - Capture the names in the order they appear.  
   - Remove duplicates within each episode.  

5. **Group episodes by team member:**  
   - Create one section per team member.  
   - Under each, list every episode in which that person appears.  
   - Omit their own name from the parenthetical guest list.  
   - Format each entry as:  
     ```
     - [Episode Title](link) (with Tim Hwang, Sandi Besen, and Mihai Criveti) — Fri, 10 Oct 2025
     ```

6. **Output format:**  
   - Display all results directly in ChatGPT as Markdown.  
   - Each team member should have a level-3 heading (`### Name`).  
   - End with a single confirmation line:  
     ```
     ✅ All entries verified against the Mixture of Experts RSS feed.
     ```

7. **No file download required.**  
   The final Markdown should render cleanly in ChatGPT and be ready for copy-paste into Slack.

### PROMPT END

---

## Step 3 — Use the Output

- Copy the Markdown result directly from ChatGPT.  
- Paste it into Slack, Notes, or any shared workspace.  
- If new IBM speakers are added later, simply append their names to the team list above and rerun this same process.

---

This prompt ensures that ChatGPT:
- Uses the most recent RSS feed of *Mixture of Experts*.  
- Groups episodes by each named team member.  
- Produces output directly in-chat in clean Markdown form.  
