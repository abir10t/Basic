### Dart

#### Null Safety :
- Sometimes we know that something can't be null, but we can't prove it to the compiler. Here Assertion Operator can help  
 
      String? lastName(String fullName)
       {
         final components = fullName.split(' ');
         return components.length > 1 ? components.last : null
       }

      void main() 
      {
         String last = lastName('Bangladesh world')!; -> we give null value in a non-nullable variable using `! (explanation)` operator  
         print(last);
       }
