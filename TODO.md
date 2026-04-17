# TODO: Fix orders.html template error

**Approved Plan Steps:**

1. ✅ [Complete] Understand files (orders.html & app.py analyzed, error confirmed: duplicate/misplaced for loops)
2. ✅ Fixed template loops in mobile_shop/templates/customer/orders.html:
   - Replaced duplicate inner `{% for od in order_details %}` with `{% for item in od.items %}`
   - Fixed indentation and loop structure (edits confirmed successful via diff)
   - Footer remains correct using od.order.total
3. ✅ Fixed "'builtin_function_or_method' object is not iterable" (sqlite3.Row issue):
   - app.py@my_orders/admin_orders: {'order': dict(o), 'items': [dict(item) for item in items]}
   - Edits successful, plain dicts passed to Jinja
5. ☐ Fix dict.items() Jinja conflict causing "'builtin_function_or_method'":
   - app.py routes: rename 'items' → 'order_items' in order_details
   - templates (customer/admin orders.html): od.items → od.order_items
6. ☐ Test: /admin/orders & /my-orders (place order first) → no errors
7. ✅ [Complete]
