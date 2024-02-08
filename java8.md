
# Java 8

### find out all the numbers starting with 1 in a list by using Stream API ?

    List<Integer> list = Arrays.asList(20,15,80,11,48,25,98,32,17);

    list.stream().map(s -> s.toString()).filter(s -> s.startsWith("1")).forEach(System.out::println);