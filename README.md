# 1337 Exam Practice Solutions 📚

Collection of common exam exercises with detailed solutions, organized by difficulty level.

## 🎯 Level 1 Exercises

### first_word 📝
Write a program that takes a string and displays its first word, followed by a newline.
- A word is a section of string delimited by spaces/tabs or by the start/end of the string.
- If the number of parameters is not 1, or there are no words, display a newline.

Examples:
```bash
$> ./first_word "FOR PONY" | cat -e
FOR$
$> ./first_word "this        ...       is sparta" | cat -e
this$
$> ./first_word "   " | cat -e
$
$> ./first_word "a" "b" | cat -e
$
$> ./first_word "  lorem,ipsum  " | cat -e
lorem,ipsum$
```
Code:
```c
#include <unistd.h>

int main(int ac, char **av)
{
    int i = 0;
    
    if (ac == 2)
    {
        while (av[1][i] == ' ' || av[1][i] == '\t')
            i++;
        while (av[1][i] != '\0' && av[1][i] != ' ' && av[1][i] != '\t')
        {
            write(1, &av[1][i], 1);
            i++;
        }
    }
    write(1, "\n", 1);
    return (0);
}
```
[View Solution](Level_01/first_word/first_word.c)

### ft_swap 🔄
Write a function that swaps the values of two integers whose addresses are passed as parameters.
```c
void ft_swap(int *a, int *b);
```
Code:
```c
void ft_swap(int *a, int *b)
{
    int temp;
    
    temp = *a;
    *a = *b;
    *b = temp;
}
```
[View Solution](Level_01/ft_swap/ft_swap.c)

### fizzbuzz 🔢
Write a program that prints numbers 1 to 100, replacing multiples of 3 with "fizz", multiples of 5 with "buzz", and multiples of both with "fizzbuzz".
Code:
```c
#include <unistd.h>

void ft_write_number(int number)
{
    if (number > 9)
        ft_write_number(number / 10);
    write(1, &"0123456789"[number % 10], 1);
}

int main(void)
{
    int i = 1;
    
    while (i <= 100)
    {
        if (i % 3 == 0 && i % 5 == 0)
            write(1, "fizzbuzz", 8);
        else if (i % 3 == 0)
            write(1, "fizz", 4);
        else if (i % 5 == 0)
            write(1, "buzz", 4);
        else
            ft_write_number(i);
        write(1, "\n", 1);
        i++;
    }
    return (0);
}
```
[View Solution](Level_01/fizzbuzz/fizzbuzz.c)

### ft_putstr 📝
Write a function that displays a string passed as parameter.
```c
void ft_putstr(char *str);
```
[View Solution](Level_01/ft_putstr/ft_putstr.c)

### ft_strcpy 📋
Write a function that copies the string src to dst.
```c
char *ft_strcpy(char *dst, char *src);
```
[View Solution](Level_01/ft_strcpy/ft_strcpy.c)

### ft_strlen 📏
Write a function that returns the length of a string.
```c
int ft_strlen(char *str);
```
[View Solution](Level_01/ft_strlen/ft_strlen.c)

### repeat_alpha ✍️
Write a program that repeats each alphabetical character based on its position in the alphabet.
[View Solution](Level_01/repeat_alpha/repeat_alpha.c)

### rev_print 🔄
Write a program that prints a string in reverse.
[View Solution](Level_01/rev_print/rev_print.c)

### rot_13 🔐
Write a program that replaces each letter with the 13th letter after it.
[View Solution](Level_01/rot_13/rot_13.c)

### rotone 🔄
Write a program that replaces each letter with the next one in alphabetical order.
[View Solution](Level_01/rotone/rotone.c)

### search_and_replace 🔍
Write a program that takes 3 arguments where the second will be replaced by the third in the first.
[View Solution](Level_01/search_and_replace/search_and_replace.c)

### ulstr 🔡
Write a program that changes the case of each letter.
[View Solution](Level_01/ulstr/ulstr.c)

## 🎯 Level 2 Exercises

### do_op ➗
Write a program that takes three strings:
- The first and third are integers
- The second is an arithmetic operator (+, -, *, /, or %)
- Display the result followed by a newline

Examples:
```bash
$> ./do_op "123" "*" 456 | cat -e
56088$
$> ./do_op "9828" "/" 234 | cat -e
42$
$> ./do_op "1" "+" 1 | cat -e
2$
$> ./do_op | cat -e
$
```
[View Solution](Level_02/do_op/do_op.c)

### inter ⚡
Write a program that takes two strings and displays, without doubles, the characters that appear in both strings.
- The display will be in the order of appearance in the first string
- The output will be followed by a newline

Examples:
```bash
$> ./inter "padinton" "paqefwtdjetyiytjneytjoeyjnejeyj" | cat -e
padinto$
$> ./inter ddf6vewg64f gtwthgdwthdwfteewhrtag6h4ffdhsd | cat -e
df6ewg4$
$> ./inter "nothing" "This sentence hides nothing" | cat -e
nothig$
```
[View Solution](Level_02/inter/inter.c)

### alpha_mirror 🪞
Write a program that displays the string with replaced letters by their mirror position in the alphabet.
[View Solution](Level_02/alpha_mirror/alpha_mirror.c)

### camel_to_snake 🐍
Write a program that converts camelCase to snake_case.
[View Solution](Level_02/camel_to_snake/camel_to_snake.c)

### ft_atoi ➡️
Write a function that converts a string to an integer.
[View Solution](Level_02/ft_atoi/ft_atoi.c)

### ft_strcmp ⚖️
Write a function that compares two strings.
[View Solution](Level_02/ft_strcmp/ft_strcmp.c)

### ft_strcspn 🔍
Write a function that returns the length of the initial segment of str1 which consists entirely of characters not in str2.
[View Solution](Level_02/ft_strcspn/ft_strcspn.c)

### ft_strdup 📋
Write a function that duplicates a string.
[View Solution](Level_02/ft_strdup/ft_strdup.c)

### ft_strpbrk 🔍
Write a function that searches a string for any set of bytes.
[View Solution](Level_02/ft_strpbrk/ft_strpbrk.c)

### ft_strrev 🔄
Write a function that reverses a string.
[View Solution](Level_02/ft_strrev/ft_strrev.c)

### ft_strspn 📏
Write a function that gets the length of a prefix substring.
[View Solution](Level_02/ft_strspn/ft_strspn.c)

### is_power_of_2 💪
Write a function that determines if a given number is a power of 2.
[View Solution](Level_02/is_power_of_2/is_power_of_2.c)

### last_word 📝
Write a program that displays the last word of a string.
[View Solution](Level_02/last_word/last_word.c)

### max 📊
Write a function that returns the largest number found in the array.
[View Solution](Level_02/max/max.c)

### print_bits 🔢
Write a function that prints the bits of a byte.
[View Solution](Level_02/print_bits/print_bits.c)

### reverse_bits 🔄
Write a function that reverses the bits of a byte.
[View Solution](Level_02/reverse_bits/reverse_bits.c)

### snake_to_camel 🐪
Write a program that converts snake_case to camelCase.
[View Solution](Level_02/snake_to_camel/snake_to_camel.c)

### swap_bits ↔️
Write a function that swaps every even and odd bit of a byte.
[View Solution](Level_02/swap_bits/swap_bits.c)

### union ⚡
Write a program that displays characters present in either of two strings without duplicates.
[View Solution](Level_02/union/union.c)

### wdmatch 🎯
Write a program that displays the first string if it's possible to construct it using characters from the second string.
[View Solution](Level_02/wdmatch/wdmatch.c)

## 🎯 Level 3 Exercises

### ft_range 📊
Write a function that returns a range of integers as an array.
```c
int *ft_range(int start, int end);
```
- This function must allocate (with malloc()) an array of integers
- This array should contain all values between start and end (including start and end)
- If start is greater than end, the range will go down

Examples:
```c
ft_range(1, 3) returns [1, 2, 3]
ft_range(-1, 2) returns [-1, 0, 1, 2]
ft_range(0, 0) returns [0]
ft_range(0, -3) returns [0, -1, -2, -3]
```
[View Solution](Level_03/ft_range/ft_range.c)

### pgcd 🧮
Write a program that takes two strictly positive integers and displays their highest common denominator.

Examples:
```bash
$> ./pgcd 42 10 | cat -e
2$
$> ./pgcd 42 12 | cat -e
6$
$> ./pgcd 14 77 | cat -e
7$
$> ./pgcd 17 3 | cat -e
1$
```
[View Solution](Level_03/pgcd/pgcd.c)

### add_prime_sum ➕
Write a program that displays the sum of prime numbers up to n.
[View Solution](Level_03/add_prime_sum/add_prime_sum.c)

### epur_str 📝
Write a program that takes a string and displays it with exactly one space between words.
[View Solution](Level_03/epur_str/epur_str.c)

### expand_str 📝
Write a program that takes a string and displays it with exactly three spaces between words.
[View Solution](Level_03/expand_str/expand_str.c)

### ft_atoi_base 🔢
Write a function that converts a string in a specific base to an integer.
[View Solution](Level_03/ft_atoi_base/ft_atoi_base.c)

### ft_list_size 📏
Write a function that returns the number of elements in a linked list.
[View Solution](Level_03/ft_list_size/ft_list_size.c)

### ft_rrange 📊
Write a function that returns a range of integers in reverse order.
[View Solution](Level_03/ft_rrange/ft_rrange.c)

### hidenp 🔍
Write a program that determines if first string is hidden in second string.
[View Solution](Level_03/hidenp/hidenp.c)

### lcm 🧮
Write a function that computes the least common multiple of two integers.
[View Solution](Level_03/lcm/lcm.c)

### paramsum 🔢
Write a program that displays the number of arguments passed to it.
[View Solution](Level_03/paramsum/paramsum.c)

### print_hex 🔢
Write a program that displays a number in hexadecimal.
[View Solution](Level_03/print_hex/print_hex.c)

### rstr_capitalizer 🔡
Write a program that capitalizes the last character of each word.
[View Solution](Level_03/rstr_capitalizer/rstr_capitalizer.c)

### str_capitalizer 🔡
Write a program that capitalizes the first character of each word.
[View Solution](Level_03/str_capitalizer/str_capitalizer.c)

### tab_mult ✖️
Write a program that displays a number's multiplication table.
[View Solution](Level_03/tab_mult/tab_mult.c)

## 🎯 Level 4 Exercises

### flood_fill 🎨
Write a function that takes a char ** as a 2-dimensional array of char, a t_point as the dimensions of this array and a t_point as the starting position of the flood. Fill all O with F starting from the given position and going up, down, right, and left.

Example:
```bash
Before flood_fill:    After flood_fill:
11111111             FFFFFFFF
10001001             F000F00F
10010001             F00F000F
10110001             F0FF000F
11100001             FFF0000F
```
[View Solution](Level_04/flood_fill/flood_fill.c)

### ft_list_remove_if 🗑️
Write a function that removes from the passed list any element whose data is "equal" to the reference data.
```c
void ft_list_remove_if(t_list **begin_list, void *data_ref, int (*cmp)());
```
[View Solution](Level_04/ft_list_remove_if/ft_list_remove_if.c)

### sort_list 📋
Write a function that sorts a linked list in ascending order using the comparison function.
```c
t_list *sort_list(t_list *lst, int (*cmp)(int, int));
```
[View Solution](Level_04/sort_list/sort_list.c)

### fprime 🔢
Write a program that displays a number's prime factors.
[View Solution](Level_04/fprime/fprime.c)

### ft_itoa 🔢
Write a function that converts an integer to a string.
[View Solution](Level_04/ft_itoa/ft_itoa.c)

### ft_list_foreach 🔄
Write a function that applies a function to each element of a linked list.
[View Solution](Level_04/ft_list_foreach/ft_list_foreach.c)

### ft_split 📋
Write a function that splits a string into words.
[View Solution](Level_04/ft_split/ft_split.c)

### rev_wstr 🔄
Write a program that displays a string's words in reverse.
[View Solution](Level_04/rev_wstr/rev_wstr.c)

### rostring 🔄
Write a program that rotates a string's words.
[View Solution](Level_04/rostring/rostring.c)

### sort_int_tab 📊
Write a function that sorts an integer array in ascending order.
[View Solution](Level_04/sort_int_tab/sort_int_tab.c)


Happy Coding! 🚀
