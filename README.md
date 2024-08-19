# DjangoORM
Django ORM = Query Sets with example 
#Django ORM
# One To One Relationships
 ```
  class Customer(models.Model):
    name = models.CharField(max_length=255)
  class Vehicle(models.Model): 
    name = models.CharField(max_length=255)
    customer = models.OneToOneField(
        Customer,
        on_delete=models.CASCADE,
        related_name='vehicle'
    )

```
```
# One To Many Relationships
  #Create your models here.
class Customer(models.Model):
    name = models.CharField(max_length=255)
class Vehicle(models.Model):
    name = models.CharField(max_length=255)
    customer = models.ForeignKey(
        Customer,
        on_delete=models.CASCADE,
        related_name='Vehicle'
    )
```
```

# Many To Many Relationships
  class Worker(models.Model):
    name = models.CharField(max_length=255)
class Machine(models.Model):
    name = models.CharField(max_length=255)
    worker = models.ManyToManyField(
        Worker,
        related_name='Machine'
    )
```
