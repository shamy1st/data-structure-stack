# Stack

![](https://github.com/shamy1st/data-structure/blob/main/images/stack.png)

--    | push | pop | peek | isEmpty
------|------|-----|------|--------
Stack | O(1) | O(1)| O(1) | O(1)

        public class Main {
            public static void main(String[] args) {
                Stack<Integer> stack = new Stack<>(10);
                stack.push(10);
                stack.push(20);
                stack.push(30);
                System.out.println(stack.pop());
                System.out.println(stack.peek());
                System.out.println(stack.isEmpty());
            }
        }

        public class Stack<T> {
            private T[] items;
            private int count;

            public Stack(int capacity) {
                items = (T[]) new Object[capacity];
            }

            public boolean isEmpty() {
                return count == 0;
            }

            public void push(T item) {
                if(count >= items.length)
                    items = (T[]) new Object[items.length * 2];
                items[count++] = item;
            }

            public T pop() {
                if(isEmpty())
                    throw new EmptyStackException();
                return items[--count];
            }

            public T peek() {
                if(isEmpty())
                    throw new EmptyStackException();
                return items[count-1];
            }
        }
