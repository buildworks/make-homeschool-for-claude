---
name: build-lessons
description: Build Make Homeschool lessons from a parent's request in their own words. Use when the parent asks for a lesson, quiz, activity, worksheet, spelling list or week of lessons on a topic for their homeschool.
---

To build lessons in Make Homeschool:

1. **Pick the course.** Call `list_courses` and use the course the parent named. If they named none, or it isn't there, ask, or offer to start one with `create_course` (a standard course unless they describe a class taught by someone outside the family, or a practice course).
2. **If they want something like an existing lesson,** read it with `get_lesson`: its `blocks` are in the exact shape the building tools take.
3. **Build the blocks the request calls for,** at most 20 per lesson: `read` (a passage), `do` (something to do), `write` (a prompt), `multiple_choice`, `matching`, `fill_in_the_blanks`, `spell_what_you_hear` (a spelling list) and `label_the_picture`.
   - Write text as simple HTML or plain text.
   - A spelling list takes up to 25 single words, each used once. Leave out words that sound alike, such as *their* and *there*. Make Homeschool speaks each word aloud.
   - A block's `intro` is shown to the student. A note for the parent goes in your reply, never in the lesson.
   - Only use `label_the_picture` if you can make the picture yourself and give it to the parent, who adds it in the app.
4. **Create it.** One lesson is `create_lesson`; several are `create_lessons` in one call. Send a fresh UUID `request_id` and, if a response is lost, resend the identical call.
5. **Reply** with each lesson's `review_url`, and say the lesson reaches no student until the parent schedules it in Make Homeschool.

The connector can't see students or their work, add students, or schedule anything. Say so if asked, rather than trying.
