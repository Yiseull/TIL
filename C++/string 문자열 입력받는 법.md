# string 문자열 입력받는 법

## 방법1 - cin
```cpp
string str;
cin >> str;
```

## 방법2 - getline()
```cpp
string str;
getline(cin, str);
```

## 방법3 - scanf()
```cpp
chat temp[10];
scanf("%s",temp);
string str = temp;
```

## 주의사항
string 타입을 scanf_s로 받을 수 없다. 
```cpp
// 이 코드는 틀린 코드!
string str;
scanf("%s", str);
```



