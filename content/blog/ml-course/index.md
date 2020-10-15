---
title: "Learning Machine Learning"
date: "2020-10-13T23:17:27Z"
description: "It's tensors all the way down"
---

One of the few odd facts that have stuck in my mind since my college days is that a matrix is actually a rank-2 tensor and tensors can be any real numbered rank (0 and up) along with any dimensionality (1 and up). For some reason I remember this even though at the time I didn't think much of it other than it was necessary knowledge to pass my linear algebra course (also I love the word "quaternion"). Since then, I've found these constructs are used in things like graphic engines and more interesting things like neural nets. And since 2015, the term "tensor" has been popularized by the widely used machine learning library [TensorFlow (TF)](https://www.tensorflow.org/).

A ways back, I followed a tutorial that used TF to solve the [MNIST handwritten number database](https://en.wikipedia.org/wiki/MNIST_database). It was interesting, but at the time I couldn't think of ways in my personal or professional projects that classification would be necessary/helpful.

Since then, my job has involved integrating with an [Random Forest](https://en.wikipedia.org/wiki/Random_forest) model implemented in R. And while I certainly don't fully understand the implications of what it does, I at least understand the use case.

But even then, I didn't see Machine Learning (ML) as accessible until recently a friend my mine showed me a small script he wrote using [Tensorforce](https://tensorforce.readthedocs.io/) which he was using to solve a wooden puzzle toy he had received as a gift. After reading over the libraries docs, I found that I had somehow missed the fact that [Tensor Flow can be used for Reinforcement Learning](https://www.tensorflow.org/agents/tutorials/0_intro_rl). Somehow I found this use case much more intriguing than general classification problems.

While reading up on modern ML, I learned that since 2016, there has been a competitor to Tensor Flow called [PyTorch](https://pytorch.org/) which has gained a sizeable foothold in the ML community, if not surpassing TF. Supposedly it's easier to develop and experiment with, but worse when it comes to running in production. For what it's worth, I spent an afternoon setting up both Tensor Flow and PyTorch on my home PC. They were about equal when it came to getting basic operation up and running, but when it came to CUDA operation in Windows, PyTorch won by a mile in ease of use/time.

After messing around with my friends code, I started looking for a modern ML course online. There were several candidates, but the one I settled on from [fast.ai](https://www.fast.ai/) showed me something rather incredible. While I spent an afternoon setting up a GPU accelerated ML dev environment, there are several, free, online Jupyter notebooks that offer _GPU acceleration_. Of course they won't be nearly as fast as running locally on my 1070, but the fact that they exist at all is amazing to me. The two I tried were:
- [Google Collab](https://colab.research.google.com/)
- [Gradient](https://gradient.paperspace.com/)

Even if I've yet to find many real world use cases for machine learning techniques, they still intrigue me. I hope to at least start the course above. The online notebooks should make taking the course incredibly accessible and I'll encourage others to give a shot. Score one for this new "run things in the cloud" future of ours. (What's that? Who said mainframes with dumb terminals were dead? Not me!)

~EOF~