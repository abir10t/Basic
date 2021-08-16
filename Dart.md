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

- Flow Analysis / definite assignment

                 int sign(int x)
              {
                int result;
                print(result); ->  we can't print here because result variable don't find any value till now.
                
                if( x >= 0 )
                  result = 1;
                  
                else
                  result = -1;

                return result;

              }
              
            
- Using non-nullable variables with class
    1. instance variable in classes must be initialized if they are not nullable
    2. if the initialized variable don't initialized with the default value, we must set it with the constructor
    

                   class BaseUrl
               {
               
                 BaseUrl(this.hostName);
                 String hostName;
                 
               }
               
 -Non-nullable named arguments
 
    
                   class BaseUrl
               {
               
                 BaseUrl({required this.hostName});
                 final String hostName;
                 
               }
               
               void printAbs({required int value})
               {
               
                  print(value.abs());
               
               }
               
      so if we use named parameter you ccan accomplish this with the required argument or a default value. Positional argument is also same.  
      
      
      
 #### Late variables
  -Declaring a non-nullable variable that’s initialized after its declaration.
  - Lazily initializing a variable.

        late String description;
        void main() {
         description = 'Feijoada!';
         print(description);
          }
  
  
  - if the temperature variable is never used, then the expensive _readThermometer() function is never called
  
         late String temperature = _readThermometer(); 
 
  
      
      

 
   

          
      
             
          
          
         
         
   
        
         
         
             
             
