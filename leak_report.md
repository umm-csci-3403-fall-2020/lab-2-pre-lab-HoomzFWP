# Leak report

basically, whenever you call the `is_clean` method you get the memory leak since `is_clean`
calls on the method `strip` that actually makes the allocation. I patched the leak by going 
into `is_clean` and freeing up the allocation once cleaned allocation was used
