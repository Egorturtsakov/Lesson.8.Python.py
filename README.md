# Lesson.8.Python.py


Номер 1:


import re
list_email = []
dict_info = {}
def email_parse(email_address):
    parsed = re.findall(r"([^@&]+)@([\w_-][\w_\.-]*\.[\w_-]{2,})$", email_address)
    if not parsed:
        raise ValueError(f"wrong email: {email_address}")
    return dict(zip(["username", "domain"], parsed[0]))

    except ValueError:
        msg = 'wrong email {}'.format(str(email_address))
        raise ValueError(msg)

    else:
        val_1 = re.findall(r"\w+", email_address)
        val_2 = val_1[0]
        val_3 = re.findall(r'@\w+[/.]\w+', email_address)
        dict_info['username'] = val_2
        dict_info["domain"] = ''.join(val_3)


    return dict_info
print(email_parse('!!!!!f@gma'))
print(email_parse('shop24@gmail.com'))


Номер 3:


def save_result_to_file(func):
    def wrapper(*args, **kwargs):
 
        return func(*args, **kwargs)
 
    return wrapper
 
 
@save_result_to_file
def factorial(num: int):
    value = 1
    for i in range(2, num + 1):
        value *= i
 
    return value
    
    
    или:
    
    
def lane_type_lower(func):

def _conv_pos(*args, **kwargs):
    args = list(args);
    args[pos] = args[pos].lower()
    return args, kwargs

def _conv_kw(*args, **kwargs):
    kwargs['lane_type'] = kwargs['lane_type'].lower()
    return args, kwargs

insp = inspect.getargspec(func)
    try:
        pos = insp.args.index('lane_type')
        conv_func = _conv_pos
    except ValueError:
        conv_func = _conv_kw

def _lane_type_lower(*args, **kwargs):
     args, kwargs = conv_func(*args, **kwargs)
     return func(*args, **kwargs)

return _lane_type_lower


Номер 4:


import random


def my_decorator(fn):
    def wrapped():
        try:
            return fn()
        except Exception as e:
            print("Error:", e)

return wrapped


@my_decorator
def my_func():
    while True:
        if random.randint(0, 4) == 0:
            raise Exception('Random!')

print('Ok')


my_func()
