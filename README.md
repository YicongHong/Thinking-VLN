# Thinking-VLN
Ideas and thoughts about the fascinating [Vision-and-Language Navigation](https://panderson.me/). :smiley:

Well... it has been three years, [WHERE IS MY SPOON???](https://bringmeaspoon.org/) :expressionless::expressionless::expressionless:

### Before worrying about the spoon

"*You shouldn't feel bad when someone else publishes a paper on the same idea you have been working on. That means we are on the right track and we have one less problem to solve. We can now focus on more interesting ideas.*" --- [Prof. Stephen Gould](http://users.cecs.anu.edu.au/~sgould/), my supervisor. :wink:

Cats are extremely helpful to research! I do [cloud cat-petting](https://space.bilibili.com/298946431/) everyday. Really hope I can have one by my side. :smiley_cat::kissing_cat:

"*I've seen things you people wouldn't believe. Attack ships on fire off the shoulder of Orion. I watched C-beams glitter in the dark near the Tannhäuser Gate. All those moments will be lost in time, like tears in rain.*" --- [Blade Runner 1982](https://www.imdb.com/title/tt0083658/).

---

### Some more serious thinkings (last update 10.Mar.2021)

Wait, be careful. Perhaps nothing make sense. And PLEASE PLEASE PLEASE CORRECT ME IF I AM WRONG. :persevere::persevere:

#### 1 - About Memory Graph


#### 2 - About Progress Monitor

I am wondering if the progress monitors defined in Self-Monitoring and SERL are learning about a dataset bias. Due to the fact that the predicted language attention weights is an input to the progress estimation module, the network could simply learns to **shift the attention weights as the agent progresses regardless whether the agent is on the right path**. :thinking: :thinking: 

Not sure if this problem is somehow reflected in Fig.(left) below, I think the correct way of visualizing the language attention is to seperate the **successful and failure cases**, or take the **actual distance to target** into account.

AuxRN is similar but they use the attended language features instead of the weights. In their paper, they mentioned "*the attention map tends to be an uniform distribution when the agent gets lost*", but I am not sure how is that shown in Fig.(mid)... :confused:

<figure class="image">
  <img src="figures/progress-monitor.png" width=100%>
</figure>
<p align="center">Fig. Language attention weights at each step (left: Self-Monitoring, mid: AuxRN, right: Recurrent-VLN-BERT).<p align="center">

Perhaps a more rigorous way to argue about progress monitor is to talk about its regularization function in traing -- a weak signal to guide the network to read the most relevant text while exploring, rather than a prediction of the navigation process. BTW, RxR dataset has much more diverse language and path lengths, should try on that. :bowtie::bowtie:

