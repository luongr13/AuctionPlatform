![alt text](https://github.com/luongr13/AuctionPlatform/blob/main/diagram.png)

```
Table Listing {
  id pk
  title char
  description textfield
  qty integer
  view_count integer
  aw_price decimal
  min_price decimal
  created_by foreignkey(User)
  start datetime
  end datetime
  origin_address char
  destination_address char
  status choices("open", "closed", "archived")
  returns_accepted boolean
  return_conditions choices('closed_box', 'open_box', 'not available')
  return_window datetime
  subcategory foreignkey(Subcategory)
  payments_accepted manytomany(PaymentType)
}

Table PaymentType {
  id pk
  name char
}

Table Subcategory {
  id pk
  name char
  category foreignnkey(Category)
}

Table Category {
  id pk
  name char
}

Table User {
  id pk
}

ref: Listing.subcategory < Subcategory.id
ref: Subcategory.category < Category.id
ref: Listing.created_by < User.id
ref: Listing.payments_accepted <> PaymentType.id
```