## find_champion(name=None, role=None, origin=None)
*Python*

### Description

The `find_champion()` function takes up to 3 arguments and loops through a list called `champion_data`, comparing the arguments to elements in the list.

* If the `name` argument matches an element's `name` in `champion_data`, that element is returned, even if the `role` and `origin` arguments do not match that element's `role` and `origin`.

* If the `name` argument does not match any element's `name` in `champion_data`, elements from `champion_data` that match the `role` and/or `origin` arguments are added to a list called `champion_suggestions`.

* If no arguments are passed to `find_champion()`, all elements of `champion_data` are added to `champion_suggestions` as potential matches.

**Returns:** An element from `champion_data` or the list `champion_suggestions`.

---

| Parameter   | Type   | Default value  | 
|-------------|--------|----------------|
| name        | str    | None           |
| role        | str    | None           |
| origin      | str    | None           | 

---

### Example

```python
champion_data = [
 {
  'name': 'ahri',
  'role': 'mid lane',
  'origin': 'vastaya'
 },
 {
  'name': 'teemo',
  'role': 'top lane',
  'origin': 'bandle city'
 },
 {
  'name':'gangplank',
  'role': 'top lane',
  'origin': 'bilgewater'
 },
 {
  'name': 'sona',
  'role': 'support',
  'origin': 'ionia'
 },
 {
  'name': 'miss fortune',
  'role': 'marksman',
  'origin': 'bilgewater'
 }
]

def find_champion(name=None, role=None, origin=None):
 champion_suggestions = []
 for champ in champion_data:
  if name:
   if champ['name'] == name:
    return [champ]
  if role:
   if champ['role'] != role:
    continue
  if origin:
   if champ['origin'] != origin:
    continue
  champion_suggestions.append(champ)
 return champion_suggestions
 ```
