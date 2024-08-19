# Django ORM
Django ORM = Query Sets with example 

### to get all objects in a model
```
>>> Customer.objects.all()
```
### to create objects
```
>>> Customer.objects.create(author=me, title='Sample title', text='Test')

```
### to filter objects
```
>>> Post.objects.filter(author=me)
>>> Post.objects.filter(published_date__lte=timezone.now())

```

### Ordering objects
```
>>> Post.objects.order_by('created_date')
```
### deleting objects
```
>>> artist =  Artist.objects.get(name='Roger Waters')
>>> artist.delete()
```

### to modify the data
```
>>> artist = Artist.objects.get(name='michael jackson')
>>> artist.genre= "rock"
>>> artist.save()
```

#Django ORM
## One To One Relationships
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

## One To Many Relationships
  #Create your models here.
 ```
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

## Many To Many Relationships

```
  class Worker(models.Model):
    name = models.CharField(max_length=255)
class Machine(models.Model):
    name = models.CharField(max_length=255)
    worker = models.ManyToManyField(
        Worker,
        related_name='Machine'
    )
```
