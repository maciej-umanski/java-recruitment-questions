# Tasks

1. <details>
    <summary>Napisz metodę, która zwróci wartość minimalną i maksymalną z tablicy liczb calkowitych.</summary>

    ```java
    public class task1 {
        public static void main(String[] args) {
            int[] numbers = {0, 1, 5, 10, 15, 5, -30, 157};
            ResultDto result = getMinAndMax(numbers);
            System.out.println(result);
        }
    
        public static ResultDto getMinAndMax(int[] numbers) {
            if(numbers.length == 0)
                throw new EmptyArgumentArrayException();
    
            int max = numbers[0];
            int min = numbers[0];
    
            for(int number : numbers) {
                if (max < number) max = number;
                if (min > number) min = number;
            }
    
            return new ResultDto(min, max);
        }
    }
    
    class EmptyArgumentArrayException extends RuntimeException {
        public EmptyArgumentArrayException() {
            super("Array passed to method is empty");
        }
    }
    
    record ResultDto(Integer min, Integer max) {}
    ```
    </details>

2. <details>
   <summary>Napisz metodę typu void, która usuwa duplikaty z listy ciągów znaków</summary>

   ```java
   public class task2 { 
        public static void main(String[] args) {
            List<String> list = List.of("test", "test1", "test2", "test");
            List<String> listWithoutDuplicates = removeDuplicates(list);
            System.out.println(listWithoutDuplicates);
        }
        public static List<String> removeDuplicates(List<String> list) {
            return list.stream().distinct().toList();
        }
   }
   ```
   </details>

3. Napisz algorytm robiący histogram z ciągu znaków.
