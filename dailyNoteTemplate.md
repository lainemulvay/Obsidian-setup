---
Morning_Exercise: 
Ice Bath: 
GEM: 
Journal: 
Meditate: 
Skin: 
Audiobook: 
Read: 
Gym:
---
[[Notes/Daily Note/<%tp.date.now("DD MMM YY (ddd)", -1, tp.file.title,"DD MMM YY (ddd)")%>|Yesterday]] <-> [[Notes/Daily Note/<%tp.date.now("DD MMM YY (ddd)", 1, tp.file.title,"DD MMM YY (ddd)")%>|Tomorrow]] 
Weekly Review: [[Notes/Weekly Review/<%moment(tp.file.title).format("gggg-[W]ww")%>|This Weeks Review]]
### 🌈 GEM Exercise
```dataviewjs
// List of gratitudes
let gratitudes1 = [];

// Extract gratitudes from pages that have them
dv.pages()
	.where(page => page.gratitude)
	.forEach(page => {
		dv.array(page.gratitude)
			.forEach(gratitude => {
				gratitudes1.push({
					message: gratitude,
					page: page
				});
				})});

let gratitudequestion1 = gratitudes1[DateTime.now().toFormat("o") % gratitudes1.length] 

dv.paragraph("###### *Gratitude:* " + gratitudequestion1.message);
```

```dataviewjs
// List of empathy messages
let empathy_list = [];

// Extract empathys from pages that have them
dv.pages()
	.where(page => page.empathy)
	.forEach(page => {
		dv.array(page.empathy)
			.forEach(empathy => {
				empathy_list.push({
					message: empathy,
				});
				})});

let empathy_question = empathy_list[DateTime.now().toFormat("o") % empathy_list.length] 

dv.paragraph("###### *Empathy:* " + empathy_question.message);
```

```dataviewjs
// List of Mindfulness Questions
let mindfulness_list = [];

// Extract Mindfulness questions from pages that have them
dv.pages()
	.where(page => page.Mindfulness)
	.forEach(page => {
		dv.array(page.Mindfulness)
			.forEach(Mindfulness => {
				mindfulness_list.push({
					message: Mindfulness,
				});
				})});

let mindfulness_question = mindfulness_list[DateTime.now().toFormat("o") % mindfulness_list.length] 

dv.paragraph("###### *Mindfulness:* " + mindfulness_question.message);
```

### Random Highlight
```dataviewjs
// List of highlights
let highlights = [];

// Extract gratitudes from pages that have them
dv.pages()
	.where(page => page.highlight)
	.forEach(page => {
		dv.array(page.highlight)
			.forEach(highlight => {
				highlights.push({
					message: highlight,
					page: page
				});
				})});

let randomhighlight = highlights[DateTime.now().toFormat("o") % highlights.length] 

dv.paragraph("###### " + randomhighlight.message);
```
### Random Vocab
```dataviewjs
// List of highlights
let vocabularies = [];

// Extract new vocab words from pages that have them
dv.pages()
	.where(page => page.vocabulary)
	.forEach(page => {
		dv.array(page.vocabulary)
			.forEach(vocabulary => {
				vocabularies.push({
					message: vocabulary,
					page: page
				});
				})});

let randomword = vocabularies[DateTime.now().toFormat("o") % vocabularies.length] 

dv.paragraph("###### " + randomword.message);
```
meaning: 
### TODO
##### ☑️ ASAP 
```dataviewjs
dv.taskList(dv.pages().file.tasks
  .where(t => !t.completed)
  .where(t => t.text.includes("#todo/asap")))
```
##### ☑️ Medium
```dataviewjs
dv.taskList(dv.pages().file.tasks
  .where(t => !t.completed)
  .where(t => t.text.includes("#todo/medium")))
```
##### ☑️ All
```dataviewjs
dv.taskList(
  dv.pages().file.tasks
    .where(t => !t.completed)
    .where(t => t.text.includes("#todo"))
    .where(t => !t.text.includes("#todo/asap"))
    .where(t => !t.text.includes("#todo/medium"))
)
```

#### ☑️ Added
- [ ]

### 📺 Most Story Worthy Moment 
- 
### 🗓️ Today's Calendar

```gEvent
date: dateFormat(today, "YYYY-MM-DD")
type: day
```
### ☕ Journalling
*Time: *


### ✍️ Other Writing


### [[Habit Tracker]]