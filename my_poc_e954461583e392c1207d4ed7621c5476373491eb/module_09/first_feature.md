# 🥇 My first feature

The first slice of my backlog's most valuable feature: listings, offered or asked for, that anyone can take.


## 📋 My listings

```csv
id,side,what,description,when,price,unit,by,taken_by
s1,offer,STAT 101 review,Two hours on chapters 3 to 5 before the quiz,Tue 19:00,10,dollars,Alex,
s2,request,STAT 101 review,Someone who passed it to walk me through chapter 4,Tue 19:00,12,dollars,Sam,
s3,offer,Essay proofreading,A careful read with notes in the margin,Thu 12:00,8,dollars,Casey,
s4,request,Essay proofreading,Read my three pages and mark what is unclear,Thu 12:00,5,dollars,Riley,
s5,offer,CS 150 pair coding,One hour of pair coding on the loops lab,Wed 17:00,60,minutes,Jordan,
s6,request,Quiet study room,Share a quiet room for exam week,Fri 09:00,1,knowledge,Morgan,
```
{: .dataset #listing }

[My listings](#)
{: .datagrid source="listing" #my_list columns="what, side, when, price, unit, by, taken_by" height="230" }

[One listing](#)
{: .form master="my_list" #one_listing editable="true" title="📝 One listing — pick it in the list" }

[🤝 Take it](#)
{: .button #take }
```python
listing = button.page.my_list.row
if not listing.taken_by:
    listing.taken_by = button.me()
```
{: .onclick }


## 🧪 My proof 

```gherkin
Feature: My first feature
  Scenario: I display the list
    When I display the list
    :::python
    self.list = getattr(self.page, "my_list", None)
    assert self.list, "no list yet — page 2 brings it"
    :::
    Then I see its listings
    :::python
    assert self.list.row_count > 0, "your list is empty — ask Bill for your listings, page 2"
    :::

  Scenario: I take one
    Given an open listing, picked in the list
    :::python
    self.list = getattr(self.page, "my_list", None)
    assert self.list, "no list yet — page 2 brings it"
    takers: list = [str(t or "").strip() for t in self.list.source.values("taken_by")]
    assert takers, "your list is empty — ask Bill for your listings, page 2"
    assert "" in takers, "every listing is taken already"
    self.list.select(takers.index("") + 1)
    :::
    When I take it
    :::python
    take = getattr(self.page, "take", None)
    assert take, "no 🤝 Take it button yet — page 3"
    take.click()
    :::
    Then it is taken
    :::python
    assert str(self.list.row.taken_by or "").strip(), "the listing is still open — your button wrote no name (signed in?)"
    :::
Then it stays taken by the same person
:::python
first_taker = str(self.list.row.taken_by or "").strip()
take = getattr(self.page, "take", None)
assert take, "no 🤝 Take it button"
take.click()
second_taker = str(self.list.row.taken_by or "").strip()
assert second_taker == first_taker, "listing was retaken – should keep first taker"
:::

```
{: .feature #feature_01 visible="true" status="pending" }