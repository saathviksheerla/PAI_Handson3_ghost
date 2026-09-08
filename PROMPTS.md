## Part A

- first try: 
```
public record UserDTO(long id, String name, String email, boolean active) {
    public static UserDTO fromUser(User user) {
        return new UserDTO(user.getId(), user.getName(), user.getEmail(), user.isActive());
    }
}
```

- second try:
```
public record UserDTO(long id, String name, String email, boolean active) {
    public static UserDTO fromUser(User user) {
        return new UserDTO(user.getId(), user.getName(), user.getEmail(), user.isActive());
    }
}
```
- - the response from agent did not change maybe it has pickedup the User.java context earlier


## Part B

- first try:
- - no compile error


## Part C
```
public Order getOrderById(long id) {
        // TODO: look up id in `store` and return it (or null).
        return store.get(id);
    }

    /** POST /orders -- create a new order, assign it the next id,
     *  store it, and return it. TODO: complete with Copilot. */
    public Order createOrder(String item, int qty) {
        // TODO: validate item/qty, allocate nextId, put in store, return.
        if (item == null || item.isEmpty() || qty <= 0) {
            throw new IllegalArgumentException("Invalid item or quantity");
        }
        Order newOrder = new Order(nextId++, item, qty);
        store.put(newOrder.id(), newOrder);
        return newOrder;
    }
```


## Part D
