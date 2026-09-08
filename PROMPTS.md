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

- PR description by agent:
Title: Add initial project structure and update prompts to include commit details
Description: 
This PR adds the initial project scaffold (Makefile, .gitignore, core classes, DTOs, basic tests, and README) and updates the prompts file to include commit details. It prepares the repository for development and testing.

What changed
- Added project skeleton: Makefile, .gitignore
- Implemented core classes: OrderController, User
- Added UserDTO and mapping from User
- Added tests for OrderController
- Updated README with setup instructions
- Updated prompts file to include commit details

Commits
- Add initial project structure with Makefile, .gitignore, and basic classes
  - https://github.com/saathviksheerla/PAI_Handson3_ghost/commit/af51355c4d5100f39deae328c4b80335c7e9cfe8
- update prompts file to include commit details
  - https://github.com/saathviksheerla/PAI_Handson3_ghost/commit/bdbcccfc330b2ae6a98ab39b6fb5430022fbe081

Notes for reviewers
- Focus review on project layout, Makefile targets, and the initial tests to confirm they run as expected.
- The prompts update is minimal — review for correctness of the added commit details format.

Testing
- Run make test (or the test command in the Makefile) to execute the provided tests.
- Verify README instructions for setup are clear and accurate.

Checklist
- [ ] Tests run and pass locally
- [ ] README setup steps verified
- [ ] CI configured (if desired) — none in this PR

What I did
I loaded PR context and fetched the branch comparison and commits to compile this title and description.

Next
If you want, I can:
- Create the PR with this title/description, or
- Expand the description with file-level diffs or CI suggestions.


- it gave too much and not accurate also, it is thinking that old diff is also part of this PR.
- I have updated the PR description before raising it.

## Part E

- prompt: suggest a branch name for this issue:
"there is no authorization for data, user and admin page are publicaly accesible, implement it"

response: "feat/implement-user-admin-authorization"

- It is a good suggestion, I would have personally like "auth/user-admin-autorization"


### summary
- AI is understanding my intent most of the times, sometimes(branch name) it is not asking for preference or my personal opinion.

- github repo link: 