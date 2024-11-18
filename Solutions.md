# HW3 Part 2: Normalization

## Warmup:
Trivial functional dependencies are those where the right side is included on the left. For example: ABC->C

To derive additional functional dependencies, we can use Armstrong's Axioms:
- Augment the existing functional dependencies by adding attributes to both sides.
- Apply transitivity to other functional dependencies.

**Q2.1**
  * Non trivial functional dependencies (in addition to given FDs): C->B, AC->B, BC->A
  * Keys: C


**Q2.2**
  * Non trivial functional dependencies (in addition to given FDs):
    - AB->D,
    - BC->A,
    - AD->C,
    - CD->B,
    - ABC->D,
    - ABD->C,
    - BCD->A,
    - ACD->B

  * Keys: AB, BC, CD, AD

# Real application:
**Q2.3**

Key in `iowa` -
`(store, itemno, date, vendor_no, invoice_line_no)`


**Q2.4**

 * ` (store, address, name, city, zipcode, store_location, store_location_adress, county_number, county, store_location_city, store_location_zip)`
 * ` (vendor_no,vendor) `
 * ` (category, category_name) `
 * ` (itemno, category, bottle_volume_ml, im_desc, state_bottle_cost, state_bottle_retail) `
 * ` (date, store, vendor_no, itemno, invoice_line_no, pack, sale_bottles, sale_dollars, sale_gallons, sale_liters) `


**Q2.5**

BCNF guarantees that the decomposition is redundency and anomaly free.

**Q2.6**

**False.** The constraint given in the question is a check constraint, that only involves the value of a single column. Functional dependencies cannot enforce check constraints. They can only enforce a relationship between the values in two or more columns.


**Q2.7** There's only one vendor

**Q2.8**

**No,** the `store` and `name` should not have a functional dependency. The design of the database may seem that the `store` uniquely identifies a `name`, meaning one `name` given a `store` number. However, this conclusion can not be made from an instance of the data.
