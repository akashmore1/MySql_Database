# CHAR and VARCHAR

1. CHAR has a fixed length.
2. VARCHAR is a bit more flexible.
3. If we have a variable of type CHAR with 4 characters, we every variable will have 4 length.
4. If we pass value more than 4, it will be truncated to 4 and if we pass less value than 4 extra spaces will be added until length is 4.
5. VARCHAR is dynamic, if we assign length 4 to varchar, and assign value less than 4 then unlike CHAR spaces will not be added.
6. Use CHAR when you know exact length of character for every variable. e.g. (yes/no) : y (or) n -> only 1 character.

# DECIMAL

```
CREATE TABLE items (
    price DECIMAL(7,4)
);
```

1. In above case maximum number of character for price is going to be 7.
2. There will be 4 decimals characters in this number.
3. So maximum number that can be saved in price is 999.9999
4. DECIMAL is used for precision.
5. If we insert very large number more than 999.9999 (in this case), mamixum value is automatically added to price i.e 999.9999
6. Also if there are more than 4 decimals then value will be rounded upto 4 decimals.
7. e.g. 6.99999999 will become 7.0000
