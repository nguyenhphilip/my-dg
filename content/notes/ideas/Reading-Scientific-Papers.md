---
title: Reading Scientific Papers
---

_I don't remember the source but these are excellent guidelines_

---

- A big part of the challenge of reading papers is deciding which ones to read. There are a lot of papers out there, and only a few will be relevant to you. Therefore, deciding __what__ to read is a nontrivial skill in itself.
- **Research papers are the most useful when you have a specific problem or question in mind**. 
    - When I first started out reading papers, I approached this the wrong way. One day, I’d suddenly decide “hmm, complexity theory is pretty interesting, let’s go on arXiv and look at some [recent complexity theory papers](https://arxiv.org/list/cs.CC/recent)“.
    - Then, I’d open a few, attempt to read them, get confused, and conclude I’m not smart enough to read complexity theory papers. Why is this a bad idea? A research paper exists to answer a very specific question, so it makes no sense to pick up a random paper without the background context. What is the problem?
    - What approaches have been tried in the past, and how have they failed? Without understanding background information like this, it’s impossible to appreciate the contribution of a specific paper.
    - __Above: Use the forward citation and related article buttons on Google Scholar to explore relevant papers.__
- **It’s helpful to think of each research paper as a node in a massive, interconnected graph.**
    - Rather than each paper existing as a standalone item, a paper is deeply connected to the research that came before and after it.
    - Google Scholar is your best friend for exploring this graph. Begin by entering a few keywords and picking a few promising hits from the first 2-3 pages. Good, this is your starting point. Here are some heuristics for traversing the paper graph:
        - **To go forward in time, look at works that cited this paper**. A paper being cited usually means one of two things: (1) the future paper uses some technique or result developed in the current paper for some other purpose, or (2) the future paper improves on the techniques in the current paper. Citations of the second type are more useful.
        - **To go backward in time, look at the paper’s introduction and related work**. This puts the paper in context of previous work. Occasionally, you find a __survey paper__ that doesn’t contribute anything novel of its own, but summarizes a bunch of previous related work; these are really helpful when you’re beginning your research in a topic.
        - **Citation count is a good indicator of a paper’s importance and merit**. If the paper has under 10 citations, take its claims with a grain of salt (even more so if it’s an arXiv preprint and not a peer-reviewed paper). Over 100 citations means the paper has made a significant contribution; over 1000 citations indicates a landmark paper in the field and is probably worth reading. Citation count is not a perfect metric, especially for very recent work, but it’s a useful heuristic that’s applicable across disciplines.
- **The first pass: High level overview**
    - Great, you’ve decided on a paper to read. Now how to read it effectively?
- **Reading a paper is not like reading a novel**. 
    - When you read a novel, you start at the beginning and read linearly until you reach the end. However, reading a paper is most efficient by hopping around the sections as appropriate, rather than read linearly from beginning to end.
- **The goal of your first reading of a paper is to first get a high level overview of the paper**, before diving into the details. As you go through the paper, here are some good questions that you should be asking yourself:
    - What is the problem being solved?
    - What approaches have been tried before, and what are their limitations?
    - What is this paper’s novel contribution?
    - What experiments were done, using what dataset? How successful were the results?
    - Can the method in this paper be applied to my problem?
    - If not, what assumptions are needed for this method to work?
- __Above: Treat each paper as a node in a massive graph of research, rather than a standalone item in a vacuum.__
- When I read a paper, I usually proceed in the following order:
    - Abstract: a long paragraph that summarizes the entire paper. Read this to decide if the rest of the paper is worth reading or not.
    - Introduction, diagrams, tables, and conclusion. Often, reading the diagrams and captions gives you a good idea of what’s going on with minimal effort.
    - If the field is unfamiliar to you, then note down any interesting references in the introduction and related works sections to explore later. If the field is familiar, then just skim these sections.
    - Read the main body of the paper: model, experiment, and discussion, without getting too bogged down in the details. If a section is confusing, skip it for now and come back to it on a second reading.
- That’s it — you’ve finished reading a paper! Now you can either go back and read it again, focusing on the details you skimmed over the first pass, or move on to a different paper that you’ve added to your backlog.
- When reading a paper, you should not expect to understand every aspect of the paper by the time you’re done. You can always refer back to the paper at a later time, as needed. Generally, you don’t need to understand all the details, unless you’re trying to replicate or extend the paper.
- **Help, I’m stuck!**
    - Sometimes, despite your best efforts, you find that a paper is impenetrable. It’s not necessarily your fault — some papers are hastily written hours before a conference deadline. What do you do now?
    - **Look for a video or blog post explaining the paper**. If you’re lucky, someone may have recorded a lecture where the author presents the paper at a conference. Maybe somebody wrote a blog post summarizing the paper ([Colah’s blog](http://colah.github.io/) has great summaries of machine learning research). These are often better at explaining things than the actual paper.
    - If there’s a lot of background terminology that don’t make sense, it may be better to consult other sources like textbooks and course lectures rather than papers. This is especially true if the research is not new (>10 years old). Research papers are not always the best at explaining a concept clearly: by their nature, they document research as it’s being done. Sometimes, the paper paints an incomplete picture of something that’s better understood later. Textbook writers can look back on research after it’s already done, and thereby benefit from hindsight knowledge that didn’t exist when the paper was written.
- **Basic statistics is useful in many experimental fields** — concepts like linear / logistic regression, p-values, hypothesis testing, and common statistical distribution. Any paper that deals with experimental data will use at least some statistics, so it’s worthwhile to be comfortable with basic stats.
