# Wahrheitstabellen



| Input A | NOT |
| :--- | :--- |
| 0 | 1 |
| 1 | 0 |

```csharp
if(a == true){
    result = false;
}else{
    result = true;
}
```

| Input A | Input B | AND | OR | NAND | XOR |  |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| 0 | 0 | 0 | 0 |  | 0 |  |
| 0 | 1 | 0 | 1 |  | 1 |  |
| 1 | 0 | 0 | 1 |  | 1 |  |
| 1 | 1 | 1 | 1 |  | 0 |  |

```csharp
if(a == true AND b == true){
    return true;
}else{
    return false;
}
```

```csharp
if(a == true OR b == true){
    return true;
}else{
    return false;
}
```

