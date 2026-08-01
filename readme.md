# README

## Resources
- **Systeme_d_exploitation_1 (S3):** [Google Drive folder](https://drive.google.com/drive/folders/1U_Q2aC2__DVjz6wjZ-JIhh9N_QyTBS62?usp=sharing)
- **Systeme_d_exploitation_2 (S4):** [Google Drive folder](https://drive.google.com/drive/folders/17nyiOMgXKQMVzq3uDNjSHESpyL1OePPF?usp=sharing)
- **Programmation_Reseaux_et_Systeme (S6):** [`./Programmation_Reseaux_et_Systeme/`](./Programmation_Reseaux_et_Systeme/)
- **Reseaux (S5):** [`./Reseaux/`](./Reseaux/)
- **Reseaux_avances (S6):** [Google Drive folder](https://drive.google.com/drive/folders/1HqWqJGTgzH4tx-ew5WKYLERoQig4hM8q?usp=sharing)

## Plan
- [ ] Systeme_d_exploitation_1 (S3)
- [ ] Systeme_d_exploitation_2 (S4)
- [ ] Programmation_Reseaux_et_Systeme (S6)
- [ ] Reseaux (S5)
- [ ] Reseaux_avances (S6)

## Contributing Notes

Each module has a `notes.md` file. When adding a note:

1. Write in Markdown. If you don't know Markdown, learn the basics (10 min) here:
   https://www.markdownguide.org/cheat-sheet/

   Or ask AI: write your notes in your favorite text editor (raw,
   unformatted is fine), then give them to an AI assistant with this
   prompt:
   ```
   I'm contributing to a shared study-notes repo. I'll give you my raw,
   unformatted notes on a topic. Your job:

   1. First, ask me two things: (a) the topic title, and (b) my GitHub
      username.
   2. Once I answer, take the notes I give you and reformat them into
      clean Markdown — fix grammar/clarity but don't remove technical
      content.
   3. Always give me the result in Markdown, using this structure:
      - `##` is reserved for the main subject title only:
        `## <topic title> — @<my-github-username>`
      - Anything else (sub-topics, categories) must use `###` or
        smaller — never `##`.
      - Use `-` for bullet points under each heading.

      Example:
      ## <topic title> — @<my-github-username>
      ### <sub-topic 1>
      - <point>
      - <point>
      ### <sub-topic 2>
      - <point>

   4. Output only the final Markdown block, nothing else — I'll paste it
      directly into notes.md.

   Here are my raw notes:
   [paste your notes here]
   ```

2. Tag your note with your GitHub handle next to the title:
   ```
   ## Topic Title — @yourusername
   ```

3. Keep one `##` heading per topic/lecture so the file stays scannable.

4. Add it to `notes.md`:
   - **No Git knowledge?** Edit `notes.md` directly in the browser on GitHub
     (open the file → pencil icon → paste your section → commit).
   - **Know the Git CLI?** Clone the repo, edit `notes.md` locally, then
     commit and push.

### Example `notes.md` structure

```markdown
# Systeme d'exploitation 1 — Notes

## Processus et Threads — @raciod
- A process is...
- Key syscalls: fork(), exec(), wait()

## Scheduling — @contributor2
- FCFS, Round Robin, Priority scheduling
```
