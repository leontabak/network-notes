# Graded Exercise 2

## LinkedIn Profile

You can find my LinkedIn profile at 
https://www.linkedin.com/in/cameron-seebach-ab7a28111

## Algorithm Lesson

I chose to look at Code Division Multiple Access (CDMA) instead of either the 
link-state or distance-vector algorithms.

Code Division Multiple Access is a multiplexing method that lets multiple 
senders talk to one reciever over the same medium at the same time. This sounds 
like magic, but in the simplest case it's not too difficult to understand.

We suppose that there is some bit-rate for a channel's data, and some faster rate
that evenly multiplies that bit-rate. The faster rate is known as a 'chipping
rate'.

We suppose that each sender, instead of sending ones and zeros, sends -1 and +1
instead.

We also suppose that each sender has a unique code, made from -1s and +1s,
with a length that matches the multiplier between the data rate and the chipping
rate.

We suppose that the channel, instead of having signals that override each other,
add together. If there's only one sender, there can only be signals made up of
+1s and -1s. If there are two senders, values from -2 to +2 can be observed in 
the medium.

When it is time to send, a sender looks at the bit it wants to send. If it is a
+1, it sends it's code at the chipping rate. If it is -1, it sends the code with
the bits swapped, -1s becoming +1s, etc.

The real magic is at the recieving end. The reciever looks through the list of
senders and their attached codes, and tries each code against the values it
sees in the channel. Essentially, by summing the values recieved for one bit,
and multiplying by each part of the code, we either come up with a -1 or +1, 
which recovers the original bit. Magic, right?

## Programming Assignment

For this assignment, I chose to implement an application-level protocol for a 
game based on the classic Pong. You can see my work at 
https://github.com/spirulence/crazy-pong.

Unfortunately, it isn't documented or tested well. I bit off more than I could 
chew given the number of hours I wanted to work on this project.