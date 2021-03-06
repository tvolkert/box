Dart Box
========

A fluent Dart persistence API inspired by SQL.
This library is still in an early phase of development.
Currently Box has two implementations.

  * Box: a very simple implementation that runs completely in-memory.
  * FileBox: an in-memory implementation that persists data to a simple JSON file.

Support for various SQL and NoSQL databases is on the roadmap.

Example:

    Box box = new FileBox('.box/test');
    List<User> users = await box.selectFrom<User>()
                                .where('name').like('C%')
                                .orderBy('name').ascending()
                                .list();
    users.forEach((user) => print(user.name)));
