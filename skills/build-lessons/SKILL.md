---
name: build-lessons
description: Build Make Homeschool lessons from a parent's request in their own words. Use when the parent asks for a lesson, quiz, activity, worksheet, spelling list or week of lessons on a topic for their homeschool.
---

To build lessons in Make Homeschool:

1. **Pick the course.** Call `list_courses` and use the course the parent named. If they named none, or it isn't there, ask, or offer to start one with `create_course` (a standard course unless they describe a class taught by someone outside the family, or a practice course).
2. **If they want something like an existing lesson,** read it with `get_lesson`: its `blocks` are in the exact shape the building tools take.
3. **Build the lesson as blocks.** A lesson is a sequence of blocks the student works through one at a time, in order, and each block type is made for one kind of material. Teach in a `read`'s text, then have the student practice it with questions, matching or a fill-in, and vary the types so the student does something between readings. Never make the lesson a picture, poster, handout, slide or infographic of its material: a picture only serves a block, such as `label_the_picture`. Build in Make Homeschool with the tools, not as a document or an image in the conversation.
4. **Build the blocks the request calls for,** at most 20 per lesson: `read` (a passage), `do` (something to do), `write` (a prompt), `watch` (a video), `memory` (a passage to learn by heart), `multiple_choice`, `matching`, `fill_in_the_blanks`, `spell_what_you_hear` (a spelling list), `label_the_picture` and `discuss` (a `question` every student answers in the lesson's Discussion, never in a test).
   - Write text as simple HTML or plain text.
   - A spelling list takes up to 25 single words, each used once. Leave out words that sound alike, such as *their* and *there*. Make Homeschool speaks each word aloud.
   - A `multiple_choice` question shows its options in the order you give them. Vary where the right answer falls from question to question; never put it first every time.
   - Everything a student sees holds only the lesson: what to learn and how to do it. Never write about Make Homeschool, these tools, or what they can't do. A note for the parent goes in your reply, never in the lesson.
   - How long a lesson takes, its pacing, what to prepare, and why it's built as it is are for the parent: say them in your reply. A student's text never says how long something should take, such as "10 minutes".
   - Put every video in a `watch` block, whatever site it's on. YouTube and public Vimeo videos play in the lesson, and any other link opens in a new tab. Never put a video's link in a `read` or a `do`.
   - For a poem, verse or definition to memorize, use `memory`. Add `recall` to have the student fill in missing words from memory; say how many, and Make Homeschool picks which.
   - Only use `label_the_picture` if you can make the picture yourself and give it to the parent, who adds it in the app.
   - Make one picture for `label_the_picture`, with no labels or numbers on it. Never make a labeled copy: set `study` and Make Homeschool shows the student each label before they try.
5. **Create it.** One lesson is `create_lesson`; several are `create_lessons` in one call. Send a fresh UUID `request_id` and, if a response is lost, resend the identical call.
6. **Read what comes back.** Each lesson's `notes` say whether each video plays in the lesson or opens in a new tab, and `waiting_for_picture` lists the `label_the_picture` blocks still waiting for the parent to add their picture. An empty list means every picture is there. If a call is refused, the message names the field you sent, such as `blocks.2.sets.0.pairs`: fix that block and send the call again.
7. **Reply** with each lesson's `review_url`, and say the lesson reaches no student until the parent schedules it in Make Homeschool.

The connector can't see students or their work, add students, or schedule anything. Say so if asked, rather than trying.
