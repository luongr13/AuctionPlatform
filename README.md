# AuctionPlatform

## Listing Model
- title_cf: CharField
- created_by_fk: fk->User
- start_dtf: DateTime
- end_dtf: DateTime
- qty_if: IntegerField
- view_count:_if: IntegerField
- aw_price_df: DecimalField
- min_price_df: DecimalField
- origin_address_cf: CharField
- status_cf: Choices["open", "closed", "archived"]
- returns_accepted_bf: BooleanField
- subcategory_fk: fk->Subcategory

## Sublisting
- listing_fk: fk->Listing
- qty_if: IntegerField 

## ListingVariation
- name_cf: CharField
- subcategory_fk: fk->Subcategory

## Subcategory Model
- name_cf: CharField
- category_fk: fk->Category

## Category Model
- name_cf: CharField