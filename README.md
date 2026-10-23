# Make Homeschool for Claude

Build homeschool courses, lessons, activities, and quizzes just how you like them. Claude can start from scratch or from a book you already have, and you review everything before your student sees it.

This plugin pairs the **Make Homeschool** connector with skills that teach Claude how to use it well: building a course around a book you own, building lessons from a request in your own words, and fixing a lesson before it's scheduled.

## What you need

A [Make Homeschool](https://makehomeschool.com) School, signing in as its owner with your parent account. Student accounts can't connect.

## Use it

1. Add the plugin, then connect **Make Homeschool** from the plugin's **Connectors** tab. You sign in to Make Homeschool and choose which School Claude may work in.
2. Ask in your own words, for example:
   - *"Make my daughter a lesson on the great horned owl: a short reading, three questions, and something to do outside."*
   - *"Add my history reader to my Bookshelf and build a lesson for each of its first five chapters."*
   - *"In that first lesson, replace the questions with five new ones and keep everything else."*
3. Claude sends back a link to each lesson so you can check it over. Nothing reaches your student until you schedule it in Make Homeschool.

## What it can and can't do

Claude can read your School's courses, lessons, Bookshelf and instructors; start courses; add books to your Bookshelf; build lessons, one or many at once; and change a lesson no student has yet. It can't see your students or their work, add students to a course, put anything on a student's day, or delete lessons or courses.

## Data

This plugin contains only instructions and a reference to Make Homeschool's server, `https://makehomeschool.com/mcp`. It stores nothing itself and sends nothing anywhere else. When you ask, Claude sends the content you ask for (lesson text, course names, a book's name) to your Make Homeschool School through that server, and reads back what's there. When Claude builds a spelling list, Make Homeschool speaks each word aloud with a text-to-speech model, on its own account, and stores the recordings in your School. See the [privacy policy](https://makehomeschool.com/privacy).

## Help

[Connect an AI agent](https://makehomeschool.com/help/connect-an-ai-agent) in Make Homeschool's Help, or info@makehomeschool.com.
