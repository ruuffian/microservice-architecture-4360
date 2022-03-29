Liam Mackay
<p align="center"><b>Microservice Bad Smells</b></p>

<p>
	So far in class, we have covered a lot of the things that a person *should* do when building a system of microservices. These include (but are not limited to) services owning their data,  wrapping services in an API to reduce dependency, bounded contexts and more. However, something we have not touched upon is the idea of a bad practice. To me, a bad practice is something that is a commonc misuse or misunderstanding of a particular technology. Below is an example of a bad practice, written in python:
</p>

```python
variable = 10

...

# Increments variable by one, then returns it
def func() -> int:
	return ++variable

print(func())
```

<p>
	This code will run and do exactly what it is meant to do. However, it is unclear at first glance where variable came from, since there could be many lines of code between its declaration and the func() call. Even though it technically runs, it would be considered bad practice to submit this code, as it is confusing to read and would be difficult to maintain.
</p>

<p>
	The following is a clearer and more maintainable way of accomplishing the same task as the above code:
</p>

```python
variable = 10

...

# Returns var + 1
def func(var: int) -> int:
	return var + 1

variable = func(variable)
```

<p>
As you can see, the second approach is much clearer in what it is doing and how it is doing it, even though it techincally accomplishes the same goal. In fact, most bad practices related to code structure tend to lean in the direction of "That technically works, but this way is much clearer or more maintainable". Other examples of bad practices that aren't directly code-related can include pushing changes directly to production branches, submitting code without testing, or over/under commenting code. This to me is the meat-and-potatoes of production-level code, as many habits that developers pick up in school or in personal projects are not punished when they are a solo dev. However, these overlooked habits tend to be very counter-productive in an enterprise environment. Hopefully, through careful study of the academic paper <a href="http://www.valentinalenarduzzi.it/papers/Paper_id24.pdf"> <i>On the Definition of Microservice Bad Smells</i> </a>, I can both learn what the widely accepted bad practices in cloud and microservice systems are, and present these techniques to the rest of the class.
</p>
