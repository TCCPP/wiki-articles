
in general, you want to have and idea how much slower than necessary you are before putting smth away under "premature optimization". don't use "premature optimization" as an excuse for not caring or not even having any idea of why it's slow, or how slow it actually is.

the full original qoute is better summarized as "don't waste time worrying about micro optimizations until you have evidence that tells you to, but do worry about macro optimizations" 
i'm not saying you did, but most people these days just throw down the "premature optimization" card as a general excuse to never think about efficiency in any context ever
which is very much the opposite of what the original quote was actually all about 

fwiw, I'm not a fan of the whole "premature optimization is evil" bs. the quote is usually taken out of context and didn't originally mean to say what it's usually used to suggest. performance is not a feature you can add in later, it's something that has to be considered while designing your code. and it's precisely the systemic issues you get by following this mindset that performance only matters sometimes that is the reason why most software is so terrible these days. 


performance is not a feature you can just add later, if your architecture wasn't designed to accommodate it.


the quote generally refers to wasting time optimizing code that's not using the most efficient algorithm yet. (verify this)

https://dl.acm.org/doi/pdf/10.1145/356635.356640

Structured Programming with `go to` Statements

> We should forget about small efficiencies, say about 97% of the time: premature optimization is the root of all evil. Yet we should not pass up our opportunities in that critical 3%. A good programmer will not be lulled into complacency by such reasoning, he will be wise to look carefully at the critical code; but only after that code has been identified. It is often a mistake to make a priori judgments about what parts of a program are really critical, since the universal experience of programmers who have been using measurement tools has been that their intuitive guesses fail.

talking about programming, not architecture
much lower-level perspective in those days
it's basically telling you to always measure, that your intuition about performance is going to be wrong
