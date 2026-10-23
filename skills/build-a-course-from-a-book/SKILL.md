---
name: build-a-course-from-a-book
description: Build a Make Homeschool course around a book or workbook the parent already has. Use when the parent names a book, curriculum, textbook or workbook, shares a photo or list of its table of contents, or asks for a lesson per chapter, unit or section.
---

To build a course around a book in Make Homeschool:

1. **Find or add the book.** Call `list_bookshelf`. If the book is there, use its `id`. If not, call `add_bookshelf_item` with its name. If that's refused because the name is already on the shelf, use the id the refusal gives.
2. **Get the sections.** Use the table of contents the parent shares (a photo, a list, or their own words). If they haven't shared one, ask which sections to cover. Never invent a book's chapters.
3. **Start the course,** unless they named an existing one (`list_courses` first; a course with that name may already exist). Call `create_course` with the course's name and `follows` set to the book's id. Leave `kind` out: a book's course is a standard course.
4. **Make every section's lesson in one call** with `create_lessons`: one lesson per section, in the book's order, each titled after its section. In each lesson, a `read` or `do` block works from the book with `work_from: { "bookshelf_item_id": <id>, "section": "<the section's own label>", "pages": "<pages, if known>" }`. Add the questions, writing prompts or activities the parent asked for.
   - Send at most 100 lessons per call; a longer book is another call.
   - Make a fresh UUID `request_id` for the batch. If the answer is lost, resend the identical call with the same `request_id`, which returns the lessons already made instead of a second set.
   - Spelling lists across the whole call speak at most 25 words in all.
5. **Reply** with the course and each lesson's `review_url`, so the parent can check them. Say plainly that nothing is on a student's day yet: the parent schedules lessons in Make Homeschool.

Don't add students, schedule lessons or delete anything; the connector can't. If the parent asks, say it's done in the app.
