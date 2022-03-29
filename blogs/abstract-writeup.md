Liam Mackay
<p align="center"><b>Microservice Bad Smells</b></p>

<p>
	So far in class, we have covered a lot of the things that a person SHOULD do when building a system of microservices. This includes (but is not limited to) services owning their data,  wrapping services in an API to reduce dependency, bounded contexts and more. However, something we have no touched upon is the idea of a bad practice. To me, a bad practice is something that is a commonc misuse or misunderstanding of some technology. An example would be something like the following, written in python:
</p>

```python
variable = 10

# Increments variable by one, then returns it
def func() -> int:
	return ++variable

print(func())
```

<p>
	This code will run fine, and do exactly what it is meant to. However, it is generally a 'bad practice' to use a global variable in this manner. Instead, the variable should be passed as an argument to the function like so:
</p>

```python
variable = 10

# Returns var + 1
def func(var: int) -> int:
	return var + 1

variable = func(variable)
```

<p>
The above code accomplishes the exact same task as before, but does so in a much clearer manner. In fact, most bad practices that have to do with code structure tend to lean in the direction of "that technically works, but this way is much clearer or more maintanable". Other examples of bad practices can include pushing changes directly to production branches, submitting code without testing, or over/under commenting code. This to me is the meat-and-potatoes of production-level code, as many habits that developers pick up in school or in personal projects actually tend to be counter-productive in an enterprise environment. Hopefully, through careful study of the academic paper <a href="http://www.valentinalenarduzzi.it/papers/Paper_id24.pdf"> <i>On the Definition of Microservice Bad Smells</i> </a> I can both learn about the widely accepted bad practices in cloud and microservice systems designs and also present design these techniques to the rest of the class.
</p>