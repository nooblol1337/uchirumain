def roman_to_arabic(inlet): 
    roman_to_arabic_simbols = {'I':1,'V':5, 
              'X':10,'L':50, 
              'C':100,'D':500,'M':1000 
              } 
    value = 0 
    g = -1 
    for i in inlet[::-1]: 
        while g + 1 < len(inlet): 
            if roman_to_arabic_simbols.get(inlet[g],0) <= roman_to_arabic_simbols.get(inlet[g+1],0): 
                value += roman_to_arabic_simbols[i] 
                g +=1 
            else: 
                value -= roman_to_arabic_simbols[i] 
                g += 1 
        if len(inlet) == 1: 
            value += roman_to_arabic_simbols[i] 
    return value 
 
 
 
 
 
 
 
 
 
 
 
 
inlet = list(input()) 
print(roman_to_arabic(inlet))
