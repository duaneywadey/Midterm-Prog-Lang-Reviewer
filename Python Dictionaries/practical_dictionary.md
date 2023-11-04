# PRACTICAL DICTIONARY EXAMPLE

```python
def work(current_status):
    current_status['money'] += 100
    current_status['energy'] -= 100

def eat(current_status):
    current_status['energy'] += 100
    current_status['money'] -= 100

def print_health_report(current_status):
    print("\nHEALTH REPORT")  # Add a newline before the health report
    for status, value in current_status.items():
        print(f"{status}: {value}")

current_status = {
    'name': 'Ivan',
    'energy': 100,
    'money': 100
}

print_health_report(current_status)
while True:
    choice = int(input("\nChoose 1 if you want to work.\nChoose 2 if you want to eat: "))
    if choice == 1:
        work(current_status)
    elif choice == 2:
        eat(current_status)

    print_health_report(current_status)

    if current_status['energy'] < 0:
        print("No energy left anymore!")
        break
    if current_status['money'] < 0:
        print("No money left anymore!")
        break

```

## How does the code work?

* The work() function is defined. It increases the money by 100 and decreases the energy key by 100 in the current_status dictionary.

* The eat() function is defined. It increases the energy by 100 and decreases the money key by 100 in the current_status dictionary.

* The print_health_report() function is defined. It prints the key-value pairs in the current_status dictionary.
