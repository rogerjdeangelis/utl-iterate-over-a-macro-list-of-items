# utl-iterate-over-a-macro-list-of-items
Iterate over a macro list of items 

    Iterate over a macro list of items                                                            
                                                                                                  
       Two Solutions                                                                              
                                                                                                  
          a. Array macro                                                                          
          b. Hand coded looping macro                                                             
                                                                                                  
    github                                                                                        
    https://tinyurl.com/y29jvaxu                                                                  
    https://github.com/rogerjdeangelis/utl-iterate-over-a-macro-list-of-items                     
                                                                                                  
    StackOverflow                                                                                 
    https://tinyurl.com/y2lmathx                                                                  
    https://stackoverflow.com/questions/57381135/iterate-over-list-of-values                      
                                                                                                  
    python-r-sas                                                                                  
    https://stackoverflow.com/users/11731250/python-r-sas                                         
                                                                                                  
    *_                   _                                                                        
    (_)_ __  _ __  _   _| |_                                                                      
    | | '_ \| '_ \| | | | __|                                                                     
    | | | | | |_) | |_| | |_                                                                      
    |_|_| |_| .__/ \__,_|\__|                                                                     
            |_|                                                                                   
    ;                                                                                             
                                                                                                  
    %symdel lst1 lst2 lst3 lst4 / nowarn;                                                         
                                                                                                  
    %let list_to_iterate=item1 item2 item3 item4;                                                 
                                                                                                  
    *            _               _                                                                
      ___  _   _| |_ _ __  _   _| |_                                                              
     / _ \| | | | __| '_ \| | | | __|                                                             
    | (_) | |_| | |_| |_) | |_| | |_                                                              
     \___/ \__,_|\__| .__/ \__,_|\__|                                                             
                    |_|                                                                           
    ;                                                                                             
                                                                                                  
    Global macro variable lst1-lst4                                                               
                                                                                                  
     %put &=lst1;                                                                                 
     %put &=lst2;                                                                                 
     %put &=lst3;                                                                                 
     %put &=lst4;                                                                                 
                                                                                                  
     LST1=item1                                                                                   
     LST2=item2                                                                                   
     LST3=item3                                                                                   
     LST4=item4                                                                                   
                                                                                                  
    *          _       _   _                                                                      
     ___  ___ | |_   _| |_(_) ___  _ __  ___                                                      
    / __|/ _ \| | | | | __| |/ _ \| '_ \/ __|                                                     
    \__ \ (_) | | |_| | |_| | (_) | | | \__ \                                                     
    |___/\___/|_|\__,_|\__|_|\___/|_| |_|___/                                                     
                                                                                                  
      __ _ _ __ _ __ __ _ _   _   _ __ ___   __ _  ___ _ __ ___                                   
     / _` | '__| '__/ _` | | | | | '_ ` _ \ / _` |/ __| '__/ _ \                                  
    | (_| | |  | | | (_| | |_| | | | | | | | (_| | (__| | | (_) |                                 
     \__,_|_|  |_|  \__,_|\__, | |_| |_| |_|\__,_|\___|_|  \___/                                  
                          |___/                                                                   
    ;                                                                                             
                                                                                                  
    %let list_to_iterate=item1 item2 item3 item4;                                                 
                                                                                                  
    %array(lst,values=&list_to_iterate);                                                          
                                                                                                  
    %put &=lst1;                                                                                  
    %put &=lst2;                                                                                  
    %put &=lst3;                                                                                  
    %put &=lst4;                                                                                  
                                                                                                  
    *_                     _                 _          _                                         
    | |__   __ _ _ __   __| |   ___ ___   __| | ___  __| |                                        
    | '_ \ / _` | '_ \ / _` |  / __/ _ \ / _` |/ _ \/ _` |                                        
    | | | | (_| | | | | (_| | | (_| (_) | (_| |  __/ (_| |                                        
    |_| |_|\__,_|_| |_|\__,_|  \___\___/ \__,_|\___|\__,_|                                        
                                                                                                  
    ;                                                                                             
                                                                                                  
    %let list_to_iterate=item1 item2 item3 item4;                                                 
                                                                                                  
    %macro slice(list_to_iterate);                                                                
      %let ii = 1;                                                                                
      %do %while (%scan(&list_to_iterate , &ii, %str( )) NE %str());                              
          %let lst&ii = %scan(&list_to_iterate , &ii, %str( ));                                   
          %global lst&ii;                                                                         
          %put &&lst&ii;                                                                          
          %let ii = %eval(&ii + 1);                                                               
      %end;                                                                                       
    %mend slice;                                                                                  
                                                                                                  
    %slice(&list_to_iterate);                                                                     
                                                                                                  
    %put &=lst1;                                                                                  
    %put &=lst2;                                                                                  
    %put &=lst3;                                                                                  
    %put &=lst4;                                                                                  
                                                                                                  
                                                                                                  
