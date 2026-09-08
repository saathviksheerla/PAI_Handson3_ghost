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
- auto enerated commit message
"
Add initial project structure with Makefile, .gitignore, and basic classes

- Created .gitignore to exclude build artifacts and libraries.
- Added Makefile for build automation, including dependencies and test commands.
- Implemented OrderController and User classes with basic functionality.
- Introduced UserDTO for data transfer and mapping from User.
- Added tests for OrderController to ensure functionality.
- Updated README with project setup instructions.
"

- writing this to push and raise a PR


## Part E

- prompt: suggest a branch name for this issue:
"there is no authorization for data, user and admin page are publicaly accesible, implement it"

response: "feat/implement-user-admin-authorization"

- It is a good suggestion, I would have personally like "auth/user-admin-autorization"


### summary
- AI is understanding my intent most of the times, sometimes(branch name) it is not asking for preference or my personal opinion.

- github repo link: 