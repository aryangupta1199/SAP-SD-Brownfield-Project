Functional Specification: S/4HANA Order-to-Cash Enhancement

Business Requirement: 
Automate and validate order entry by building/configuring a Fiori-based process for NextGen Manufacturing.

Functional Design:
1. Sales Order Entry
   - User: Sales Rep launches “Manage Sales Orders” Fiori app.
   - Process:
      - System offers type-ahead for customer and material.
      - Validates at entry: credit exposure, product availability, minimum order, pricing conditions.
   - Config Steps:
      - Define Sales Document Type: OR (Standard Order)
      - Enhance validations: Add user-exit USEREXIT_CHECK_VBAP for item level.
      - Price simulation and retrieve schedule lines (ATP)
   - Output: Order confirmation sent via Email Output Management (converted to new S/4HANA output type).

2. Pricing Simplification
   - Reduce from 18 to 10 condition types (PR00, K004, TAX, etc).
   - Map legacy conditions to new ones during migration.

3. Customer-Vendor Integration (CVI)
   - Migrate all KNA1/KNVV customer data to Business Partner (BP).
   - Validate using BUPA transaction post-migration.

Testing:
- Test data: Customer 100022, Material PUMP-5000, Quantity 10
- Expected: Order saved, price auto-calculated, credit check OK, output sent.

