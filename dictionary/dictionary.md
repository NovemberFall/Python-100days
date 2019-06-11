# dictionary : unordered 
```python
my_dict = {'key1': 'value1', 'key2':'value2'}                
my_dict                #{'key1': 'value1', 'key2': 'value2'}
my_dict['key1']                #'value1'

prices_lookup = {'apple':2.99, 'oranges':1.9, 'milk':5.80}               
prices_lookup['apple']                #2.99


# inside a dicitionary:

d = {'k1':123, 'k2':[0,1,2], 'k3':{'insidekey':100}}
 d['k2']               #[0, 1, 2]
 d['k2'][2]             # 2
d['k3']                #{'insidekey': 100}
d['k3']['insidekey']                #100
                #
                #
                #
                #
```

# assign to other container
```python
d = {'key1':['a','b','c']}
mylist = d['key1']
mylist                            #['a', 'b', 'c']

letter = mylist[2]
   letter                   # c
d                            #{'key1': ['a', 'b', 'c']}
d['key1'][2].upper()                            #'C'

d = {'k1':100, 'k2':200}
d                            #{'k1': 100, 'k2': 200}

# insert a elment
d['k3'] = 300                            
d                            #{'k1': 100, 'k2': 200, 'k3': 300}

# change the value of a key
d['k1'] = 'NEW VALUE'                            
d                           #{'k1': 'NEW VALUE', 'k2': 200, 'k3': 300}

d = {'k1': 100, 'k2': 200, 'k3': 300}
# print keys() values() items()
d.keys()                            #dict_keys(['k1', 'k2', 'k3'])
 d.values()                           #dict_values([100, 200, 300])
 d.items()                           #dict_items([('k1', 100), ('k2', 200), ('k3', 300)])
```