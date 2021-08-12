### Dart

#### Null Safety :
- https://www.youtube.com/watch?v=aZtjcbsdwTo
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
       
- Flow Analysis
     
      int absolutevalue(int? value )
       {
       return value.abs(); -> thats not okay, we must do null check, because the return type is not nullable(int)
       }

       void main()
        {
      
        }
        
     Solution :
         in dart 2.8 :
         
            int absolutevalue(int? value )
            {
               return value?.abs() ?? 0;  -> `value?` : 1. An Expression whose value can be null must be null-checked before it can be dereferenced., 2. if value null then return 0; 
            }

        
   
     in 2.9 :
     

       int absolutevalue(int? value )
       {
         if ( value == null)
           return 0;

         return value.abs();
       }

      
             
          
          
         
         
   
        
         
         
             
             
