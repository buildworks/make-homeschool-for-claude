---
name: revise-a-lesson
description: Change a Make Homeschool lesson that no student has yet. Use when the parent asks to fix, edit, shorten, reorder, rename or replace part of a lesson, or to remove or add a block.
---

To change a lesson in Make Homeschool:

1. **Read it first** with `get_lesson`. Note its `version` and its `outline`, which numbers every block, including ones you can't build (such as a video the parent added).
2. **Send the whole new block list** to `revise_lesson`, with that `version`:
   - keep each block you aren't changing as `{ "keep": N }`, using its number from the outline;
   - put new blocks where they belong, in the same shape the building tools take;
   - to replace a block, leave it out and put its new version where it was;
   - add `title` only to rename the lesson.

   **Every block you don't keep is removed, with anything it holds,** such as a file or picture the parent added. So keep every block you aren't changing, and confirm with the parent before removing anything they didn't ask to remove.
3. **If the change is refused because the lesson changed,** read it again with `get_lesson` and work from the new version. If you were retrying after a lost response, look there first: your change may already be in.
4. **If the lesson is already on a student's day,** it can't be changed here. Offer to build a new lesson instead with `create_lesson`.
5. **Reply** with the lesson's `review_url` and what changed.

Never use `revise_lesson` to empty or delete a lesson, and don't try to delete lessons or courses. The parent does that in the app.
