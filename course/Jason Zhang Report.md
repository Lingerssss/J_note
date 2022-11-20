

1. 

```python
        if ('call_waiter') in request.form:
            flash('Waiter called over!', category='success')
            if (current_user.is_authenticated and current_user.email.endswith("@OAXACA.com")):
                flash('Table 1 has called you over', category='success')
```

This is a piece of code that doesn't seem complicated, but I think it makes a lot of sense.

First, there was no clear understanding of how to distinguish the different roles of the user: customer/server/kitchen. This was our first attempt at distinguishing characters. In the process of writing this code, I had a clear understanding and shared my views with the team, which was recognized by everyone.

Second, this code identifies a way to distinguish roles by the suffix of the user's registered mailbox. This method is simple, efficient, and very realistic. Because generally only enterprise employees can register corresponding enterprise email.

Finally, this code gave me a new perspective on how different systems interact.



2.

EI (A): client-table-name, dish-table-name, ingredien-table-namet: 3

EO (B): menu for client user, costs of dish, warning for insufficient ingredients:3

EQ (C): register:3

EIF (D): client, dish, ingredient: 4

ILF (E): Dictionary: 0



Weighting FP Categories：

| Item   | Simple | Weighting Factor Average | Complex |
| ------ | ------ | ------------------------ | ------- |
| EI(A)  | 3      | 4                        | 6       |
| EO(B)  | 4      | 5                        | 7       |
| EQ(C)  | 3      | 4                        | 6       |
| EIF(D) | 7      | 10                       | 15      |
| ILF(E) | 5      | 7                        | 10      |



Assuming average complexity for each FP category: 

UFC = 4A + 5B + 4C + 10D + 7E = 12 + 15 + 12 + 40 = 79

Assuming the costs of dish, warning for insufficient ingredients are complex, register is simple (everything else being average): 

UFC = 4A + (5 * 1 + 7 * 2) + 3C + 10D + 7E = 16 + 19 + 9 + 40 = 84



3.

Scrum provides management thinking, guiding principles and foundations for building development teams, managing product development schedules, requirements management, etc., such as managing requirements with and only a prioritized list. I learned a lot in this team project.

In fact, during the first two iterations, I was skeptical of this development process. Because it feels like we spend a lot of time "using Scrum".

However, as the development went on, I found that Trello Board was particularly helpful to the development of the team, because we assigned specific tasks to individuals and ensured that high-priority tasks could be completed as soon as possible.
In summary, Scrum keeps the team project running efficiently and steadily.



4.

What I want to talk about is "Refactoring." Because I now think refactoring is very important. On team projects, everyone has their own code style and habits. And that often becomes a barrier to working with others. Examples include ambiguous naming, complex and lengthy single functions.

In the case of naming fields and functions, I later realized the importance of the seemingly simple matter of naming. We don't have to clutter up our code base with confusing and meaningless names that make it hard to understand other people's code.

I then started refactoring and renaming portions of each iteration. A good name is better than multiple line comments. A good function name, for example, makes it easy to understand what the function is doing without having to look at the implementation.

