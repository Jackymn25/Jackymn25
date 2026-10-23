# Will AI Replace Us? My Thoughts on Research, Language Models, and the Next Generation of Engineers

[English](./README.md) | [中文](./README.zh-CN.md)

Recently, I've seen a lot of discussions about whether AI will eventually replace researchers, software engineers, or even most jobs that involve intellectual work.

I'm still a computer science student myself. I've worked on a few machine learning research projects and participated in software system development. But to be honest, I'm not particularly anxious about the future of AI.

It's not because I think AI isn't powerful enough. Quite the opposite. I believe AI will fundamentally change how we conduct research and build software, potentially bringing human productivity to a level that would have been difficult to imagine before.

However, I've always felt that we need to distinguish between two things: **reusing knowledge that humanity has already accumulated, and creating knowledge that humanity has not yet established.**

I believe AI has demonstrated enormous potential in the former. But when it comes to the latter, there are still some important limitations worth thinking about.

This is essentially how I understand AI, scientific research, and the future of engineers in our generation.

## 1. AI's Greatest Contribution to Research: Making Scientific Discovery Less Dependent on Luck

Looking back at the history of science, I've noticed that many important discoveries involved at least some degree of luck.

We've all heard the story of Newton watching an apple fall from a tree. There are also countless examples of scientists noticing something unusual during an experiment, recording the observations, proposing a hypothesis, building a model, and eventually discovering a previously unknown pattern.

Of course, scientific discoveries are never purely a matter of luck. Recognizing an anomaly and explaining it requires years of accumulated knowledge and experience.

But there's always one prerequisite: **you first need an opportunity to notice the phenomenon.**

Human attention is limited.

A researcher cannot spend 24 hours a day, 365 days a year, staring at a monitoring instrument. Many anomalies that might have scientific value could have appeared in experimental data long ago, only to be overlooked because nobody happened to notice them.

AI has the potential to change this.

It can continuously monitor experimental data, identify unusual patterns, and connect those anomalies with previous research. When something unexpected appears, it may even attempt to organize the available evidence, propose possible explanations, and suggest follow-up experiments, much like a scientist would.

Of course, detecting an anomaly is not the same as proving a scientific conclusion. But at the very least, we may no longer miss so many potentially important observations simply because our attention is limited.

**Rather than directly making discoveries on behalf of scientists, I think AI's more important contribution is dramatically increasing the probability that something worth discovering actually gets noticed.**

Beyond this, there's another issue that I consider even more important: scientific literature.

My mother has a PhD, and we once talked about how doctoral students produce research. She told me that one of the most important things is reading a large amount of literature.

As you keep reading, you gradually develop a sense of the field. You begin to understand which problems have already been solved, which methods have been attempted, how different studies relate to one another, and where new opportunities might exist.

But there's a limit to how many papers a person can read in a lifetime.

Even a professor who has spent decades studying a particular field can hardly know every detail of it.

I sometimes wonder whether an extremely important finding might have been written down a hundred years ago, on a piece of paper that has since turned yellow with age.

Perhaps that finding received little attention at the time. It might take decades, or even centuries, before another researcher comes across it and realizes its significance.

Or imagine a PhD student spending months thinking about a completely new research question, without realizing that half of the problem was already solved in a paper published several decades ago.

Not because the student isn't intelligent enough, but because they simply don't have the ability to find and read every potentially relevant paper.

AI could change this to a considerable extent.

A system consisting of multiple AI agents could continuously search the literature around a research question, analyze findings, identify connections between different methods, and check whether existing work could be reused.

Research from two seemingly unrelated fields might even become connected through large-scale AI-assisted retrieval and analysis.

To me, this is where AI becomes particularly valuable in scientific research.

**It doesn't necessarily need to discover new scientific laws on its own. Simply helping humanity reorganize, connect, and make better use of existing knowledge could already lead to enormous progress.**

## 2. But AI Still Has Its Limitations

At this point, it might sound as though AI could already solve many of the problems researchers face.

However, I believe these capabilities still have their limitations.

To understand those limitations, we need to look at how language models work.

My basic understanding of an LLM is that it learns patterns from large amounts of training data, with next-token prediction as the core objective behind text generation.

Although modern language models have demonstrated increasingly sophisticated reasoning abilities through pretraining, post-training, and additional computation during inference, their training objective is not directly to discover scientific truth.

Instead, they learn statistical relationships, linguistic structures, and the knowledge and patterns represented within those structures.

There's an experience from my own research that made me think about this.

I once built an academic literature screening classifier using a BERT model developed by Microsoft.

At the time, I wanted to understand how much the model depended on a particular sentence containing information that seemed critical to the classification.

So, for each paper, I removed a sentence that I personally considered very important to the decision, then examined how the model's prediction changed.

The result surprised me.

**For approximately 99% of the papers, the model still produced the correct classification even after that sentence was removed.**

My initial reaction was that the model's decisions were not as dependent on individual details as I had expected.

Of course, this experiment doesn't prove that language models cannot understand details. It's also possible that the information needed for classification was distributed throughout the article, so removing one sentence was not enough to change its overall meaning.

But the experience made me seriously consider a question:

**Is the model actually understanding a particular decisive detail, or is it making its judgment based on the most prominent statistical patterns in the text?**

For many classification tasks, the latter may already be sufficient.

For example, if an article is largely discussing the effectiveness of a treatment for a certain disease, the model might still classify it correctly based on the remaining content, even after a seemingly important sentence is removed.

But scientific discovery is different.

Sometimes, the most valuable part of a paper is precisely the unexpected result that contradicts the overall trend.

A seemingly insignificant experimental detail might eventually become the starting point of an entirely new theory.

This made me realize something: being good at recognizing overall patterns does not necessarily mean a model can reliably identify which small deviations have genuine scientific value.

Another experience reinforced this understanding.

In April of this year, I worked in a research lab, where I helped maintain and develop a data pipeline that used deployed LLMs to extract information from research materials.

At the time, the lab disabled sampling during model inference by setting `do_sample=False`.

The reason was simple: to make the same input produce consistent results as reliably as possible under the same execution conditions.

Scientific research requires reproducibility.

You can't have a model extract one conclusion from a paper today, only to produce a different answer when you run the same process tomorrow.

But for conversational products, we sometimes want a certain degree of diversity in generated responses.

For example, when you say "Hello" to an AI, you don't necessarily want it to respond in exactly the same way every single time.

These two applications made me realize that the stability and diversity of model outputs are themselves something we can adjust and balance.

However, regardless of how we configure the model, **a highly probable answer, or an answer that can be consistently reproduced, is not necessarily scientifically correct.**

More importantly, the patterns learned from existing data may also become a limitation when the model explores new problems.

I'm not saying that AI is fundamentally incapable of generating something that never explicitly appeared in its training data.

In fact, generalization is precisely the ability to handle unfamiliar problems by combining, abstracting, and transferring existing knowledge.

But I do wonder how much we can rely on AI when a problem requires us to genuinely step outside an existing framework of knowledge, or even challenge an assumption that has been widely accepted for decades.

Especially in scientific research, a truly valuable discovery isn't always about finding the answer that best fits our existing knowledge.

Sometimes, it's about realizing that **the way we understood the problem in the first place might have been wrong.**

And that is not quite the same task as predicting the most likely answer.

## 3. Can Multi-Agent Systems Solve This Problem?

Someone might ask: if a single AI model tends to be constrained by existing patterns, why not let many AI agents think about the problem together?

Today, many agent-based systems, including some systems designed for complex mathematical reasoning, are exploring approaches along these lines.

I have a fairly intuitive way of understanding multi-agent systems:

**To some extent, they're an example of brute force working surprisingly well.**

Imagine we're trying to solve a software system design problem.

Suppose we've identified three possible technical approaches, and each approach has ten different implementation strategies.

We could assign thirty agents to explore those thirty possibilities independently, implement and test their solutions, analyze the results, and ultimately select the best one.

This could certainly be very effective.

In traditional software development, it would be roughly equivalent to hiring thirty engineers to implement thirty different solutions, then running experiments to determine which one performs best.

In the past, this might have been completely impractical because of the human labor involved.

But AI makes large-scale parallel exploration increasingly possible.

Agents can also organize their exploration into a search tree.

One agent proposes an initial solution, while other agents explore different directions, examining particular details in greater depth. As the process continues recursively, the system can investigate an increasingly large number of possibilities.

The advantage is obvious.

If a single reasoning process tends to overlook certain details, we may be able to compensate by exploring additional paths, repeatedly validating results, and comparing different solutions.

But there's an equally obvious problem.

**Cost.**

Exploring thirty approaches might be feasible. What about three hundred? Three thousand?

More complex problems may involve combinations of decisions across multiple design dimensions, causing the search space to grow very quickly.

And the cost isn't just the price of generating tokens.

You still need to verify whether the results are correct, execute experiments, maintain computational environments, manage dependencies between different agents, and deal with errors that multiple agents might make in common.

If thirty agents use similar models, similar training data, and similar reasoning strategies, they may all overlook the same important direction.

That leads to another question: randomness and diversity of thought.

Some people might argue that we can solve this simply by introducing more randomness, encouraging different agents to produce different answers.

To some extent, that's true.

But I believe the diversity of human thinking is much more than randomly generating different sequences of words.

Every person has different genetics, childhood experiences, educational backgrounds, living environments, and interactions with the physical world.

Over time, these differences shape distinct ways of thinking.

As a result, different researchers may approach the exact same problem from completely different perspectives.

But if a thousand agents are essentially different instances of the same foundation model, giving them different roles, prompts, and random seeds does not necessarily mean we've created a thousand researchers with genuinely independent experiences.

To simulate that kind of diversity more closely, we might need agents with long-term memory, different environmental feedback, accumulated personal experiences, and perhaps even the ability to continuously update their own capabilities.

From an engineering perspective, this isn't necessarily impossible. But building and maintaining such a system over a long period would clearly be far more expensive and complicated than simply making a thousand parallel LLM calls.

So I'm not arguing that multi-agent systems are useless.

Quite the opposite. For high-value scientific questions, difficult mathematical problems, and complex engineering designs, large-scale search and verification may be well worth the cost.

But I don't believe this automatically means we can apply unlimited computational resources to every ordinary problem in the future and easily replace everyone's work.

Especially when a problem doesn't have a clearly defined evaluation criterion, generating a thousand possible solutions and knowing which one is genuinely valuable are still two different things.

## 4. What Does This Mean for Researchers and Engineers?

Let's return to the original question: will AI eventually replace our jobs?

I think the first thing AI changes is not necessarily whether we still need to work, but **which level of problems humans should spend their time solving.**

One of my former research supervisors once told me that researchers might spend 90% of their time on tedious literature reviews and preparatory work, leaving only 10% of their effort for meaningful data analysis.

Of course, those numbers were probably an exaggeration, but I think they reflect a real problem in scientific research.

To answer a valuable research question, we often need to spend an enormous amount of time completing work that isn't particularly creative.

Searching for literature, cleaning data, reproducing code, debugging environments, and organizing experimental results.

All of these tasks are important, but they aren't necessarily where researchers want to spend most of their intellectual energy.

AI could dramatically reduce the cost of completing them.

A literature review that previously required months of work might eventually be turned into a fairly comprehensive first draft within days.

Experimental code that used to require extensive manual implementation could also be generated, executed, and revised much more quickly with AI.

So what should researchers focus on instead?

My understanding is that we will increasingly move toward higher-level questions.

In the past, we might have spent most of our effort figuring out how to reproduce an algorithm.

In the future, we may care more about why the algorithm works, what assumptions it relies on, and whether the entire architecture should be redesigned.

In the past, we might have focused primarily on how to analyze experimental data.

In the future, as AI handles more of the analysis, we may devote more attention to designing the experiments themselves and questioning existing theoretical frameworks.

I would even argue that **one of the most important abilities in future scientific research may gradually shift from performing a particular analysis to identifying which questions are worth studying and how entirely new research frameworks should be constructed.**

I think software engineering will follow a similar pattern.

Imagine a company with an established software architecture that needs to add a new feature to its existing system.

The requirements are clear, the interfaces are already defined, and the implementation patterns are well established.

I believe this kind of work will become increasingly easy to automate with AI.

Because, in a sense, it mainly involves reusing existing knowledge within an already defined framework.

But what happens when we encounter an entirely new problem?

For example, suppose a company wants to develop a new distributed multi-agent system. Engineers would need to reconsider task scheduling, state management, fault tolerance, and coordination between agents.

Or perhaps we're trying to design a new compiler and runtime system for the next generation of large language models.

These problems often don't have established standard solutions.

Of course, AI can help us propose approaches, write prototypes, and potentially even discover designs that humans haven't considered.

But engineers still need to determine what problem the system is actually supposed to solve, how to evaluate the trade-offs between different designs, and whether a proposed solution is reliable in a real-world environment.

This reminds me of how deep learning architectures have evolved.

The transition from RNNs to Transformers was not simply a matter of adding a few lines of code to an existing model.

The emergence of the Transformer came from researchers reconsidering how sequence modeling should work.

If recurrent architectures face limitations in parallel computation and modeling long-range dependencies, could we organize the computation in a fundamentally different way?

That line of thinking eventually led to a new architecture.

I wouldn't claim that AI will never be able to design a similarly novel architecture. In fact, AI is already capable of participating in neural architecture search and algorithm discovery.

But this example illustrates that technological progress isn't just about implementing existing solutions more efficiently.

**Sometimes, the most important breakthrough comes from redefining how a problem should be solved in the first place.**

And that's where I believe the next generation of engineers will continue to find value.

## 5. What Is the Mission of Our Generation?

I often compare AI to books.

Of course, AI is much more than a book. It can retrieve information, reason, write code, use tools, and interact with real environments.

But from the perspective of passing knowledge between generations, they have something in common.

Humans began recording knowledge so that the next generation wouldn't have to repeat every discovery and experiment made by the previous one.

That's why we developed books, libraries, databases, the internet, and now AI.

Every generation can build on the knowledge established by those who came before it and use that foundation to accomplish something new.

We don't need to reinvent operating systems or derive every mathematical theorem from scratch before we can begin researching new computer systems.

Previous generations have already built those foundations for us.

But that doesn't mean future generations have nothing left to do.

Quite the opposite. The more knowledge humanity accumulates, the higher our starting point becomes, and the more opportunities we have to solve problems that were previously beyond our reach.

AI is simply accelerating this process.

It allows us to understand previous achievements more quickly, implement existing techniques more efficiently, and test whether an idea is feasible in much less time.

That's why I'm not particularly worried about my future as a computer science student.

Imagine you're currently studying computer science at a university. After graduation, you join a company as an intern and help develop a traditional software system.

Perhaps a few years later, AI will be capable of writing much of the code that you were previously responsible for.

But at the same time, another company might approach you and say:

"We're developing a new multi-agent computing platform. I noticed you've studied artificial intelligence and have practical experience with distributed systems. Would you be interested in joining us?"

Or perhaps:

"We're designing a new compiler for the next generation of machine learning models. You understand how traditional compilers work, and you've also done machine learning research. Would you like to get involved?"

To me, this isn't an unrealistic scenario.

As a technology becomes more mature, standardized, and automated, humans tend to develop new requirements on top of it.

In the past, we needed large numbers of engineers to maintain low-level infrastructure. As that infrastructure became more mature, we began building systems of even greater scale and complexity.

AI will similarly create new engineering problems, and solving those problems will require new research and engineering capabilities.

Of course, this doesn't mean every existing position will transition smoothly, or that AI won't make the job market more competitive in certain fields.

I simply don't think we should imagine future engineering work as an unchanged continuation of the jobs we have today.

If AI can eventually implement many existing functionalities, then what we really need to learn shouldn't be limited to writing those functionalities manually.

Instead, we should understand why systems are designed in certain ways, why particular methods work, when they fail, and how to construct new solutions when existing approaches are no longer sufficient.

**The purpose of learning existing knowledge has never been merely to reproduce it. It is to develop the ability to create the next generation of technology.**

## Conclusion

So my attitude toward AI is actually quite straightforward.

I'm extremely optimistic about its potential to improve productivity in scientific research and engineering.

It can read, search, organize, and connect information tirelessly. It can help us uncover research findings that were previously overlooked, and it can dramatically reduce repetitive work in software development.

Multi-agent systems may even enable large-scale parallel exploration of possibilities that humans previously couldn't afford to investigate because of time and resource constraints.

But I believe that **becoming better at reusing existing knowledge does not automatically mean becoming capable of independently judging entirely new problems.**

At least based on my current understanding, AI still needs to deal with challenges involving training distributions, evaluation criteria, real-world feedback, and computational costs.

And perhaps the most important human abilities will increasingly involve figuring out which questions to ask, how to reframe problems, and what is actually worth creating.

AI may become far more capable than I can imagine today. It may also gradually overcome many of the limitations that I currently consider important.

I don't want to claim that AI will never be able to accomplish certain things.

But I still believe that every generation has its own new problems to solve.

Previous generations built the information systems, computer architectures, and machine learning theories we rely on today. Our generation has the opportunity to use AI to understand and build upon those achievements more quickly.

And then, on top of that foundation, continue creating the next generation of technology.

**That is what I believe we should be doing. And that is why, even though I'm still just a student, I'm not particularly anxious about AI replacing my future.**
