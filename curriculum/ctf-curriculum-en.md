# Heungsadan Cyber Academy: CTF Curriculum

**Published:** November 2, 2026

**Author:** James

A 10-month program for Heungsadan youth and adults to learn cybersecurity
fundamentals and prepare to compete as a CTF team. Participants meet twice a
month for 20 regular meetings, with two weeks of self-directed assignments
between meetings. The curriculum is based on Carnegie Mellon University's free
CyLab Security Academy (formerly picoCTF). The legal standards referenced in
this program are those of the United States.

## Program at a glance

The program has six stages, 10 months, and 20 regular meetings. Participants
advance after meeting the goals for each stage.

| Stage | Duration (meetings) | CyLab Academy areas | Goal for advancing |
| --- | --- | --- | --- |
| 0. Fundamentals and Ethics | 1 month (1–2) | Introductory General Skills | Submit the ethics pledge and solve 10 General Skills problems |
| 1. Linux, Scripting, and the Hacker Mindset | Months 2–3 (3–6) | General Skills | Solve 25 General Skills problems and write a first Python solution script |
| 2. Data, Cryptography, and Evidence | Months 4–5 (7–10) | Cryptography, Forensics | Solve 10 cryptography and 10 forensics problems; pass the first mock competition |
| 3. Web Exploitation | Months 6–7 (11–14) | Web Exploitation | Solve 10 web problems and attack a vulnerable web app built by participants |
| 4. Inside Programs | Months 8–9 (15–18) | Reverse Engineering, Binary Exploitation, required AI, optional Blockchain | Solve 8 reverse engineering, 5 binary exploitation, and 5 AI problems; choose a team specialty |
| 5. Competition Practice | Month 10 onward (19–20) | All areas; live Events | Compete as a team in a live CyLab Academy event |

## Mission and code of ethics

Following Dosan Ahn Chang-ho's teaching to **"first build strength,"** we
develop ethical security practitioners whose strength comes from character,
skill, and teamwork. Every participant learns the values before the techniques.

All participants—and a parent or guardian for minors—sign the following pledge
before the end of Stage 0:

1. I will test only systems I own or have written permission to test, such as
   CTF platforms, our lab, and my own virtual machines.
2. I will never attack school, home, public-sector, or company networks, even
   "just to try it."
3. I will not share flags or solutions during a live competition.
4. If I discover a real vulnerability, I will report it to the instructor and
   never exploit it.
5. I understand that unauthorized access is a crime punishable under the
   United States' Computer Fraud and Abuse Act (CFAA) and state computer-crime
   laws. Minors are not exempt.

All legal and regulatory standards in this program are based on U.S. law.
Participants under 18 also provide parental consent. Participant information
will be kept to a minimum and handled in accordance with applicable U.S.
student and children's privacy rules, including FERPA and COPPA.

### Principles for using AI tools

Use AI as a teacher that helps you learn, not as a tool that finds answers for
you—the practice of **Mu-sil** (integrity and truthfulness).

- Use AI freely to explain concepts, interpret error messages, and answer
  syntax questions.
- Do not paste an entire problem into AI to obtain its flag, even during
  practice.
- In each write-up, disclose how and where you used AI.
- During competitions, follow that competition's AI-use rules.

## Participants and program format

- **Who can participate:** Anyone age 13 or older, youth or adult. No coding
  experience is required. CyLab Academy identifies critical thinking as the
  only prerequisite.
- **Enrollment:** Open to anyone, with no enrollment cap. If participation
  grows, one mentor for every eight participants is recommended during labs.
- **Regular meetings:** Twice a month (every other week), three hours per
  meeting, for 20 meetings over 10 months.
- **Between meetings:** Two weeks of CyLab Classroom assignments, with about
  two hours of self-directed study per week. Mentors answer questions in the
  Discord server.
- **Cost:** Free. CyLab Academy is free, and a laptop with a web browser is
  sufficient through Stage 3.
- **Platform:** One CyLab Academy Classroom per cohort, with an invitation
  code, Batch Register for participants without email addresses, and
  Assignments with due dates.

### Heungsadan's four principles

| Principle | Meaning | What it means for a hacker |
| --- | --- | --- |
| Mu-sil (務實) | Strive for truth and practical integrity | Do not copy flags or solutions; report findings honestly |
| Yeok-haeng (力行) | Put effort into action | Practice consistently and learn by solving problems yourself |
| Chung-ui (忠義) | Loyalty and righteousness | Protect teammates, systems, and users; keep your commitments |
| Yong-gam (勇敢) | Courage | Take on difficult problems, admit what you do not know, and ask for help |

## Regular meeting format

Each meeting follows the same schedule:

| Time | Activity | Description |
| --- | --- | --- |
| 0:00–0:15 | Character and values | Connect a Dosan quote or an ethics case to the day's topic |
| 0:15–0:45 | Review of the previous assignment | Work together on problems participants found difficult over the past two weeks |
| 0:45–1:30 | Concept lesson | The instructor demonstrates two new techniques |
| 1:30–2:30 | Lab | Participants work in pairs on assigned CyLab problems |
| 2:30–2:50 | Solution presentations | Two pairs present their solution process in a write-up |
| 2:50–3:00 | Next assignment | Assign work in Classroom and choose a challenge problem |

Each meeting's assignment covers the following two weeks. Assign easier
problems first from the relevant Challenge Library area, then add one
intermediate challenge problem.

## Meeting-by-meeting curriculum

### Stage 0: Fundamentals and Ethics (Meetings 1–2)

| Meeting | What we learn | Two-week assignment (CyLab area) |
| --- | --- | --- |
| 1 | What cybersecurity and CTFs are; the code of ethics; Dosan's "first build strength" principle; computer and internet fundamentals (files, bits, bytes, IP addresses, and ports) | Create an account, join Classroom, and solve 5 General Skills problems |
| 2 | Binary, hexadecimal, ASCII, and Base64; problem-solving habits (read carefully, search, and document solutions) | 10 cumulative General Skills problems and a first write-up |

### Stage 1: Linux, Scripting, and the Hacker Mindset (Meetings 3–6)

| Meeting | What we learn | Two-week assignment (CyLab area) |
| --- | --- | --- |
| 3 | Terminal basics (`ls`, `cd`, `cat`), `grep`, `find`, pipes, and redirection | General Skills |
| 4 | Permissions, users, processes, SSH, and Bash scripting fundamentals | General Skills |
| 5 | Python 1 and 2: variables, loops, strings, and working with files and bytes | General Skills |
| 6 | Git, connecting to remote challenges with netcat, review, and a practice scrimmage | Reach 25 cumulative General Skills problems and submit a solution script |

### Stage 2: Data, Cryptography, and Evidence (Meetings 7–10)

| Meeting | What we learn | Two-week assignment (CyLab area) |
| --- | --- | --- |
| 7 | Classical ciphers (Caesar, Vigenère, and substitution), XOR, and the difference between encoding and encryption | Cryptography |
| 8 | Hashes, password-cracking fundamentals, RSA concepts, and attacks using small numbers | Cryptography |
| 9 | File forensics (file signatures, `strings`, metadata, and hex editors) and image steganography | Forensics |
| 10 | Network forensics (Wireshark and packet captures) and the first mock competition | Complete 10 cryptography and 10 forensics problems |

### Stage 3: Web Exploitation (Meetings 11–14)

| Meeting | What we learn | Two-week assignment (CyLab area) |
| --- | --- | --- |
| 11 | How the web works (HTTP, HTML, JavaScript, and browser developer tools); cookies, sessions, and vulnerable logins | Web Exploitation |
| 12 | SQL fundamentals, SQL injection, and cross-site scripting (XSS) | Web Exploitation |
| 13 | Command injection, path manipulation, and the Burp Suite proxy | Web Exploitation; build a vulnerable web app as a project |
| 14 | Attack another team's web app and take the second mock competition | Reach 10 web problems |

### Stage 4: Inside Programs (Meetings 15–18)

| Meeting | What we learn | Two-week assignment (CyLab area) |
| --- | --- | --- |
| 15 | C fundamentals and compilation; assembly, registers, and the stack | Reverse Engineering |
| 16 | Disassembly and decompilation with Ghidra; tracing execution with GDB | Reverse Engineering |
| 17 | Introduction to buffer overflows, format-string bugs, and ROP | Binary Exploitation |
| 18 | **Required AI security:** how AI models work, prompt injection, adversarial examples, and model inversion; third mock competition and team specialty selection. **Optional Blockchain:** smart-contract bugs as a self-directed assignment | Solve 5 AI problems; optionally study Blockchain; reach 8 reverse engineering and 5 binary exploitation problems |

### Stage 5: Competition Practice (Meetings 19–20)

| Meeting | What we learn | Two-week assignment (CyLab area) |
| --- | --- | --- |
| 19 | Team strategy (challenge triage, role assignment, and shared notes) and a three-hour mock CTF | Work on Learning Paths in weaker areas and revisit past competition problems |
| 20 | Review the mock CTF, hold a completion ceremony, and run a Heungsadan mini CTF | Compete in a live event, such as CyLab Academy Events |

## Projects

Each stage ends with a hands-on project: participants who have built something
understand how it can be broken. Projects become part of each participant's
portfolio.

The capstone puts Dosan's spirit into practice: **"Those who have built their
strength teach the next generation."**

| Stage | Project | Deliverable |
| --- | --- | --- |
| 0 | Hacker's notebook | A personal solution journal, in Markdown or Notion, used throughout the year |
| 1 | Utility script | A Python script that automatically decodes Base64, hexadecimal, binary, and ROT13 |
| 2 | Cryptography challenge | Each participant creates one cryptography or steganography challenge for another participant |
| 3 | Vulnerable web app | Each team builds a login site with one hidden bug, then swaps apps and attacks |
| 4 | Crackme | Each team creates a C program with a hidden password for another team to reverse engineer |
| 5 (capstone) | Heungsadan mini CTF | Run a 10-problem CTF for newer members, complete with a solution guide and scoreboard |

## Growing as a CTF competitor

Participants progress through four ranks. At Stage 5, each four-person team
covers the major areas.

### Four-person competition team roles

- **Web lead:** Web Exploitation
- **Cryptography and forensics lead:** Cryptography and Forensics
- **Pwn and reverse engineering lead:** Reverse Engineering and Binary Exploitation
- **Captain (generalist):** General Skills, AI, challenge triage, scoreboard
  monitoring, and shared-note management

### Ranks

| Rank | Requirements | What you can do |
| --- | --- | --- |
| Rookie | Sign the ethics pledge and participate in a 10-problem mock competition | Participate |
| Player | Solve 40 problems across three areas | Join a competition team |
| Specialist | Solve 15 intermediate or advanced problems in one area | Lead that area for the team |
| Captain | Become a Specialist, publish 5 write-ups, and mentor 1 Rookie | Lead the team and run the Heungsadan mini CTF |

### Competitions to try, from easiest to hardest

1. Mock competitions (Scrimmages) in our CyLab Academy Classroom, available at
   any time.
2. CyLab Academy live events, such as the 2026 Spring event, which typically
   runs for about 10 days.
3. Other CTF competitions chosen by the team once participants reach Player
   rank or above. Check each competition's age and team rules.

## Assessment

This is not an exam-based program. Growth is assessed through problem solving,
write-ups, and character.

Before each regular meeting, the instructor reviews Class Progress and Class
Activity. Participants who have stopped progressing during a two-week period
are paired with a mentor.

| Area | Weight | How it is measured |
| --- | ---: | --- |
| Problem-solving progress | 40% | CyLab Classroom Report (scores and progress by area, exported as CSV) |
| Write-ups | 25% | One every two weeks; reviewed for clarity and honesty |
| Mock competitions | 15% | Classroom Scrimmage results (easy: 1 point, intermediate: 2 points, hard: 3 points) |
| Projects | 10% | Stage project submissions and presentations |
| Character | 10% | Attendance, helping teammates, and honoring the ethics pledge |

## Instructor preparation checklist

- Read the CyLab Academy Educator Guide.
- Create an instructor account and one Classroom for each cohort.
- Register participants without email addresses through Batch Register and
  store account information securely.
- Confirm that participants can access CyLab Academy from the meeting venue's
  network.
- Collect ethics pledges from participants and, for minors, their parents or
  guardians.
- Set the dates for all 20 regular meetings for the year (every other week).
- Create Stage 0 Assignments with due dates.
- Recruit mentors (recommended: one per eight participants) and set up a
  Discord server with announcement, question, and area-specific channels.
- Prepare a Linux virtual machine with Ghidra, GDB, and Python before Stage 4.

## Sources and contacts

- CyLab Security Academy: areas, Learning Paths, Events, and Classrooms
- CyLab Academy Educator Guide: Classroom features, mock competition scoring,
  and prerequisites
- CyLab Academy Challenge Library
- CMU student ambassador inquiries: [contact@cylabacademy.org](mailto:contact@cylabacademy.org)
