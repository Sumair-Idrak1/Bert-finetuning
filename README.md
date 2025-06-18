# Bert4TC Finetuning
# Assignment 3
My groupmate Iqra Rathore (SP25-Rai-018) and I, Sumair Javed (SP25-Rai-019), worked on a project to teach a smart computer program called BERT how to figure out if movie reviews from the IMDb website are good (positive) or bad (negative). We did this by fine-tuning BERT. The fine-tuning techniques employed were standard fine-tuning and the BERT4TC method with gradual unfreezing.

This project took a lot of time because we faced a big problem early on: our first IMDb dataset was wrong. This made our program overfit, meaning it became too good at remembering our training examples but couldn't guess correctly on new reviews. It was tough to find the right dataset, and fixing this took quite a while before we could even properly train the program.

We tried two main ways to fine-tune BERT:

## Our Regular Way:
First, we cleaned up the movie reviews by removing things like internet links and fixing shortened words. Then, we just fine-tuned BERT directly on these clean reviews.

## The Paper's Way (BERT4TC):
We also tried a more advanced method from a research paper. This involved adding a special "helper sentence" to each movie review. For example, if a review was positive, we'd add, "This review shows good feelings." Then, we fine-tuned BERT using both the review and this helper sentence together. This helped BERT understand the sentiment better.

However, training the Paper's Way was very slow. Even one round of training (called an epoch) took about two hours. Because we could only run it for one epoch, our model either didn't learn enough or it became too focused on guessing "negative" every time. This showed us that training for too short a time meant the model wasn't properly fine-tuned.

For both methods, we made sure to prepare the data carefully so BERT could learn as well as possible, despite the early challenges and the long training times.