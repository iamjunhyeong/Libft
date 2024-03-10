# **Libft**

##### Your very first own library

<br>

# Chapter 3

## 3.2 Part 1 - Libc functions

##### _To begin, you must redo a set of functions from the `libc`. Your functions will have the same prototypes and implement the same behaviors as the originals. They must comply with the way they are defined in their `man`. The only difference will be their names. They will begin with the "`ft_`" prefix. For instance, `strlen` becomes `ft_strlen`._

당신은 `libc`에서 일련의 함수들을 구현 해야합니다. 당신의 함수는 원래 함수와 동일한 원형을 가지고 동일한 동작을 구현해야합니다. 함수들은 `man`에서 정의 된 방식에 따라 준수해야합니다. 유일한 차이점은 이름입니다. 함수의 이름은 `"ft_"`로 시작합니다. 예를 들어, `"strlen"`은 `"ft_strlen"`이 됩니다.

> ⚠️
>
> ##### Some of the functions’ prototypes you have to re-code use the "restrict" qualifier. This keyword is part of the c99 standard. It is therefore forbidden to include it in your prototypes and to compile it with the flag `-std=c99`.
>
> 여러분이 재구현하여야 하는 함수들 중 일부는 원본의 프로토타입에 "restrict" 한정자가 사용됩니다. 이 키워드는 c99 표준에 해당하므로, 여러분의 라이브러리 프로토타입들에 이 키워드를 포함시키고 `std=c99` 플래그를 사용하여 컴파일하는 것은 금지됩니다.

##### _You must write your own function implementing the following original ones. They do not require any external functions:_

아래의 함수들을 다시 구현하세요. 이 함수들은 외부 함수를 필요로 하지 않습니다 :

- `isalpha`, `isdigit`, `isalnum`, `isascii`, `isprint`
- `strlen`, `memset`, `bzero`, `memcpy`, `memmove`, `strlcpy`, `strlcat`, `strncmp`
- `toupper`, `tolower`, `strchr`, `strrchr`
- `memchr`, `memcmp`, `strnstr`, `atoi`

##### _In order to implement the two following functions, you will use "`malloc()`":_

다음 두 함수들은 `malloc()` 을 사용하여 구현하세요 :

- `calloc`, `strdup`

<br>

## 3.3 Part 2 - Additional functions

##### _In this second part, you must code a set of functions that are either not included in the `libc`, or included in a different form. Some of these functions can be useful to write Part 1’s functions._

두 번째 파트에서는, `libc`에 포함되어 있지 않거나 다른 형식으로 포함된 함수들을 재구현하여야 합니다. 다음 함수들 중 일부는 Part 1 함수를 작성할 때 도움이 될 거에요.

<br>

| **함수 이름**                | ft_substr                                                                                                                                                                                                                                                                                                                                |
| ---------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **프로토타입**               | `char *ft_substr(char const *s, unsigned int start, size_t len);`                                                                                                                                                                                                                                                                        |
| **제출할 파일**              | -                                                                                                                                                                                                                                                                                                                                        |
| **매개변수**                 | `s: 부분 문자열 (substring) 을 생성할 원본 문자열` <br> `start: 부분 문자열의 맨 처음 인덱스` <br> `len: 부분 문자열의 최대 길이`                                                                                                                                                                                                           |
| **반환값**                   | `부분 문자열. 할당 실패 시, NULL`                                                                                                                                                                                                                                                                                                        |
| **사용가능한 <br>외부 함수** | `malloc`                                                                                                                                                                                                                                                                                                                                 |
| **설명**                     | _Allocates (with malloc(3)) and returns a substring from the string ’s’. The substring begins at index ’start’ and is of maximum size ’len’._ <br> `malloc(3) 을 이용하여 메모리를 할당받은 후, 원본 문자열 's' 로부터 부분 문자열을 생성하여 반환합니다.` <br>`부분 문자열은 인덱스 'start' 부터 시작하며, 최대 길이 'len'을 갖습니다.` |

<br>

| **함수 이름**                | ft_strjoin                                                                                                                                                                                                                                |
| ---------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **프로토타입**               | `char *ft_strjoin(char const *s1, char const *s2);`                                                                                                                                                                                       |
| **제출할 파일**              | -                                                                                                                                                                                                                                         |
| **매개변수**                 | `s1: 접두 문자열 (prefix string)` <br> `s2: 접미 문자열 (suffix string)`                                                                                                                                                                  |
| **반환값**                   | `새로운 문자열. 할당 실패 시, NULL`                                                                                                                                                                                                       |
| **사용가능한 <br>외부 함수** | `malloc`                                                                                                                                                                                                                                  |
| **설명**                     | _Allocates (with malloc(3)) and returns a new string, which is the result of the concatenation of ’s1’ and ’s2’._ <br> `malloc(3) 을 이용하여 메모리를 할당받은 후, 문자열 's1' 과 's2' 를 이어붙인 새로운 문자열을 생성하여 반환합니다.` |

<br>

| **함수 이름**                | ft_strtrim                                                                                                                                                                                                                                                                           |
| ---------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **프로토타입**               | `char *ft_strtrim(char const *s1, char const *set);`                                                                                                                                                                                                                                 |
| **제출할 파일**              | -                                                                                                                                                                                                                                                                                    |
| **매개변수**                 | `s1: 양 쪽을 잘라낼 원본 문자열` <br> `set: 제거될 문자들의 집합`                                                                                                                                                                                                                     |
| **반환값**                   | `문자가 제거된 문자열. 할당 실패 시, NULL`                                                                                                                                                                                                                                           |
| **사용가능한 <br>외부 함수** | `malloc`                                                                                                                                                                                                                                                                             |
| **설명**                     | _Allocates (with malloc(3)) and returns a copy of ’s1’ with the characters specified in ’set’ removed from the beginning and the end of the string._ <br> `malloc(3) 을 이용하여 메모리를 할당받은 후, 's1'의 양 쪽 끝에서 'set'에 지정된 문자들이 제거된 문자열 사본을 반환합니다.` |

<br>

| **함수 이름**                | ft_split                                                                                                                                                                                                                                                                                                                                                                  |
| ---------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **프로토타입**               | `char **ft_split(char const *s, char c);`                                                                                                                                                                                                                                                                                                                                 |
| **제출할 파일**              | -                                                                                                                                                                                                                                                                                                                                                                         |
| **매개변수**                 | `s: 분할할 문자열` <br> `c: 구분자 (delimiter)`                                                                                                                                                                                                                                                                                                                         |
| **반환값**                   | `split을 통해 분할된 문자열의 배열. 할당 실패 시, NULL`                                                                                                                                                                                                                                                                                                                   |
| **사용가능한 <br>외부 함수** | `malloc, free`                                                                                                                                                                                                                                                                                                                                                            |
| **설명**                     | _Allocates (with malloc(3)) and returns an array of strings obtained by splitting ’s’ using the character ’c’ as a delimiter. The array must be ended by a NULL pointer._ <br> `malloc(3) 을 이용하여 메모리를 할당받은 후, 구분자 'c' 를 기준으로 문자열 's'를 분할하여 그 결과를 담은 새로운 문자열 배열을 반환합니다. 문자열 배열의 끝은 NULL 포인터로 끝나야 합니다.` |

<br>

| **함수 이름**                | ft_itoa                                                                                                                                                                                                                                                                       |
| ---------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **프로토타입**               | `char *ft_itoa(int n);`                                                                                                                                                                                                                                                       |
| **제출할 파일**              | -                                                                                                                                                                                                                                                                             |
| **매개변수**                 | `n: 변환할 정수`                                                                                                                                                                                                                                                             |
| **반환값**                   | `정수를 표현하는 문자열. 할당 실패 시, NULL`                                                                                                                                                                                                                                  |
| **사용가능한 <br>외부 함수** | `malloc`                                                                                                                                                                                                                                                                      |
| **설명**                     | _Allocates (with malloc(3)) and returns a string representing the integer received as an argument. Negative numbers must be handled._ <br> `malloc(3) 을 이용하여 메모리를 할당받은 후, 인자로 받은 정수를 나타내는 문자열을 반환합니다. 음수 또한 무조건 처리되어야 합니다.` |

<br>

| **함수 이름**                | ft_strmapi                                                                                                                                                                                                                                                                                                                                                                                                       |
| ---------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **프로토타입**               | `char *ft_strmapi(char const *s, char (*f)(unsigned int, char));`                                                                                                                                                                                                                                                                                                                                                |
| **제출할 파일**              | -                                                                                                                                                                                                                                                                                                                                                                                                                |
| **매개변수**                 | `s: 함수를 적용할 문자열` <br> `f: 문자열의 각 문자에 적용할 함수`                                                                                                                                                                                                                                                                                                                                             |
| **반환값**                   | `원본 문자열에서 함수 'f'를 성공적으로 적용하여 생성된 결과 문자열. 할당 실패 시, NULL`                                                                                                                                                                                                                                                                                                                          |
| **사용가능한 <br>외부 함수** | `malloc`                                                                                                                                                                                                                                                                                                                                                                                                         |
| **설명**                     | _Applies the function ’f’ to each character of the string ’s’ , and passing its index as first argument to create a new string (with malloc(3)) resulting from successive applications of ’f’._ <br> `문자열 's' 의 각 문자를 순회하며 함수 'f'를 적용하고, 해당 문자의 인덱스를 함수 'f'의 첫 번째 인자로 사용합니다. 각 문자에 함수가 적용된 새로운 문자열을 생성합니다 (malloc(3) 을 이용하여 메모리를 할당)` |

<br>

| **함수 이름**                | ft_striteri                                                                                                                                                                                                                                                                                                                                                                                                    |
| ---------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **프로토타입**               | `void ft_striteri(char *s, void (*f)(unsigned int, char*));`                                                                                                                                                                                                                                                                                                                                                   |
| **제출할 파일**              | -                                                                                                                                                                                                                                                                                                                                                                                                              |
| **매개변수**                 | `s: 함수를 적용할 문자열` <br> `f: 문자열의 각 문자에 적용할 함수`                                                                                                                                                                                                                                                                                                                                           |
| **반환값**                   | `없음`                                                                                                                                                                                                                                                                                                                                                                                                         |
| **사용가능한 <br>외부 함수** | `없음`                                                                                                                                                                                                                                                                                                                                                                                                         |
| **설명**                     | _Applies the function f to each character of the string passed as argument, and passing its index as first argument. Each character is passed by address to f to be modified if necessary_ <br> `문자열 's' 의 각 문자를 순회하며 함수 'f'를 적용하고, 해당 문자의 인덱스를 함수 'f'의 첫 번째 인자로 사용합니다. 또한 각 문자의 주소값이 'f' 함수의 두 번째 인자로 사용되며, 경우에 따라 수정될 수 있습니다.` |

<br>

| **함수 이름**                | ft_putchar_fd                                                                                                  |
| ---------------------------- | -------------------------------------------------------------------------------------------------------------- |
| **프로토타입**               | `void ft_putchar_fd(char c, int fd);`                                                                          |
| **제출할 파일**              | -                                                                                                              |
| **매개변수**                 | `c: 출력할 문자` <br> `fd: 값이 쓰여질 파일 식별자 (file descriptor)`                                         |
| **반환값**                   | `없음`                                                                                                         |
| **사용가능한 <br>외부 함수** | `write`                                                                                                        |
| **설명**                     | _Outputs the character ’c’ to the given file descriptor._ <br> `제공받은 파일 식별자에 문자 'c'를 출력합니다.` |

<br>

| **함수 이름**                | ft_putstr_fd                                                                                                  |
| ---------------------------- | ------------------------------------------------------------------------------------------------------------- |
| **프로토타입**               | `void ft_putstr_fd(char *s, int fd);`                                                                         |
| **제출할 파일**              | -                                                                                                             |
| **매개변수**                 | `s: 출력할 문자열` <br> `fd: 값이 쓰여질 파일 식별자 (file descriptor)`                                      |
| **반환값**                   | `없음`                                                                                                        |
| **사용가능한 <br>외부 함수** | `write`                                                                                                       |
| **설명**                     | _Outputs the string ’s’ to the given file descriptor._ <br> `제공받은 파일 식별자에 문자열 's'를 출력합니다.` |

<br>

| **함수 이름**                | ft_putendl_fd                                                                                                                                         |
| ---------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------- |
| **프로토타입**               | `void ft_putendl_fd(char *s, int fd);`                                                                                                                |
| **제출할 파일**              | -                                                                                                                                                     |
| **매개변수**                 | `s: 출력할 문자열` <br> `fd: 값이 쓰여질 파일 식별자 (file descriptor)`                                                                              |
| **반환값**                   | `없음`                                                                                                                                                |
| **사용가능한 <br>외부 함수** | `write`                                                                                                                                               |
| **설명**                     | _Outputs the string ’s’ to the given file descriptor, followed by a newline._ <br> `제공받은 파일 식별자에 문자열 's'를 출력하고, 개행을 출력합니다.` |

<br>

| **함수 이름**                | ft_putnbr_fd                                                                                                 |
| ---------------------------- | ------------------------------------------------------------------------------------------------------------ |
| **프로토타입**               | `void ft_putnbr_fd(int n, int fd);`                                                                          |
| **제출할 파일**              | -                                                                                                            |
| **매개변수**                 | `n: 출력할 정수` <br> `fd: 값이 쓰여질 파일 식별자 (file descriptor)`                                       |
| **반환값**                   | `없음`                                                                                                       |
| **사용가능한 <br>외부 함수** | `write`                                                                                                      |
| **설명**                     | _Outputs the integer ’n’ to the given file descriptor._ <br> `제공받은 파일 식별자에 정수 'n'를 출력합니다.` |

<br>

# Chapter 4

## Bonus part

##### _If you completed the mandatory part, you’ll enjoy taking it further. You can see this last section as Bonus Points._

필수 파트의 과제를 모두 수행하셨다면, 그보다 더 나아가는 것도 좋은 경험이 될 거에요. 이 마지막 섹션을 통해 보너스 점수를 얻어 보세요.

##### _Having functions to manipulate memory and strings is very useful, but you’ll soon discover that having functions to manipulate lists is even more useful._

메모리와 문자열을 다루는 함수는 아주 유용하게 사용할 수 있죠. 지금부터 여러분은 리스트를 다루는 함수가 얼마나 더 유용한 지 알 수 있을 거에요.

##### _`make bonus` will add the bonus functions to the `libft.a` library._

`make bonus` 는 `libft.a` 라이브러리에 보너스 함수들을 추가합니다.

##### _You have to use the following structure to represent node of your list. Add its declaration to your `libft.h` file:_

리스트에 노드를 표현하기 위해 다음과 같은 구조체를 사용하세요. 이 구조체를 `libft.h` 파일에 선언해야 합니다.

```c
typedef struct s_list
{
    void          *content;
    struct s_list *next;
}              t_list;
```

##### _The members of the t_list struct are:_

다음은 t_list 구조체의 각 필드에 대한 설명입니다 :

- ##### _`content` : The data contained in the node.<br>The `void *` allows to store any kind of data._

  `content`: 노드에 포함된 데이터.<br>`void *` 를 통해 어떠한 자료형의 값도 담을 수 있습니다.

- ##### _`next` : The next element’s address or `NULL` if it’s the last one._

  `next`: 다음 요소의 주소값. 만약 해당 요소가 마지막이라면, `NULL`을 가리킵니다.

 > ⚠️ <br>
 > 
 > ##### _The bonus part will only be assessed if the mandatory part is PERFECT. Perfect means the mandatory part has been integrally done and works without malfunctioning. If you have not passed ALL the mandatory requirements, your bonus part will not be evaluated at all._
 > 
 > 보너스는 필수로 구현해야 하는 파트가 **완벽할 때**만 평가될 것입니다. '완벽함' 이란, 모든 필수 파트가 전부 구현되어 있어야 하며 오작동하는 부분이 없어야 함을 의미합니다. 필수로 구현해야 하는 파트에서 **만점**을 받지 못한다면, 보너스 항목은 채점되지 않습니다.
 > 

##### _Implement the following functions in order to easily use your lists._

다음의 함수들은 리스트를 쉽게 다룰 수 있도록 돕습니다.


<br>

| **함수 이름**                | ft_lstnew                                                                                                                                                                                                                                                                                                                                                                                 |
| ---------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **프로토타입**               | `t_list *ft_lstnew(void *content);`                                                                                                                                                                                                                                                                                                                                                       |
| **제출할 파일**              | -                                                                                                                                                                                                                                                                                                                                                                                         |
| **매개변수**                 | `content: 새로운 요소에 들어갈 content`                                                                                                                                                                                                                                                                                                                                                        |
| **반환값**                   | `새로운 요소 (element)`                                                                                                                                                                                                                                                                                                                                                                   |
| **사용가능한 <br>외부 함수** | `malloc`                                                                                                                                                                                                                                                                                                                                                                                  |
| **설명**                     | _Allocates (with malloc(3)) and returns a new element. The variable ’content’ is initialized with the value of the parameter ’content’. The variable ’next’ is initialized to NULL._ <br> `malloc(3) 을 통해 메모리를 할당하고 새로운 요소를 반환합니다. 요소 내의 변수 'content' 는 인자로 받아온 'content' 로 초기화되어야 합니다. 요소 내의 변수 'next'는 NULL로 초기화되어야 합니다.` |

<br>

| **함수 이름**                | ft_lstadd_front                                                                                         |
| ---------------------------- | ------------------------------------------------------------------------------------------------------- |
| **프로토타입**               | `void ft_lstadd_front(t_list **lst, t_list *new);`                                                      |
| **제출할 파일**              | -                                                                                                       |
| **매개변수**                 | `lst: 리스트의 맨 앞에 위치한 요소`<br>`new: 리스트에 추가할 요소`                                        |
| **반환값**                   | `없음`                                                                                                  |
| **사용가능한 <br>외부 함수** | `없음`                                                                                                  |
| **설명**                     | _Adds the element ’new’ at the beginning of the list._ <br> `요소 'new'를 리스트의 맨 앞에 추가합니다.` |

<br>

| **함수 이름**                | ft_lstsize                                                                              |
| ---------------------------- | --------------------------------------------------------------------------------------- |
| **프로토타입**               | `int ft_lstsize(t_list *lst);`                                                          |
| **제출할 파일**              | -                                                                                       |
| **매개변수**                 | `lst: 리스트의 맨 앞에 위치한 요소`                                                      |
| **반환값**                   | `리스트의 길이`                                                                         |
| **사용가능한 <br>외부 함수** | `없음`                                                                                  |
| **설명**                     | _Counts the number of elements in a list._ <br> `리스트에 포함된 요소의 개수를 셉니다.` |

<br>

| **함수 이름**                | ft_lstlast                                                                                    |
| ---------------------------- | --------------------------------------------------------------------------------------------- |
| **프로토타입**               | `t_list *ft_lstlast(t_list *lst);`                                                            |
| **제출할 파일**              | -                                                                                             |
| **매개변수**                 | `lst: 리스트의 맨 앞에 위치한 요소`                                                            |
| **반환값**                   | `리스트의 맨 마지막 요소`                                                                     |
| **사용가능한 <br>외부 함수** | `없음`                                                                                        |
| **설명**                     | _Returns the last element of the list._ <br> `리스트의 맨 마지막에 위치한 요소를 반환합니다.` |

<br>

| **함수 이름**                | ft_lstadd_back                                                                                    |
| ---------------------------- | ------------------------------------------------------------------------------------------------- |
| **프로토타입**               | `void ft_lstadd_back(t_list **lst, t_list *new);`                                                 |
| **제출할 파일**              | -                                                                                                 |
| **매개변수**                 | `lst: 리스트의 맨 앞에 위치한 요소의 포인터`<br>`new: 리스트의 맨 끝에 추가할 요소`                 |
| **반환값**                   | `없음`                                                                                            |
| **사용가능한 <br>외부 함수** | `없음`                                                                                            |
| **설명**                     | _Adds the element ’new’ at the end of the list._ <br> `요소 'new'를 리스트의 맨 뒤에 추가합니다.` |

<br>

| **함수 이름**                | ft_lstdelone                                                                                                                                                                                                                                                                                                                                                      |
| ---------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **프로토타입**               | `void ft_lstdelone(t_list *lst, void (*del)(void *));`                                                                                                                                                                                                                                                                                                            |
| **제출할 파일**              | -                                                                                                                                                                                                                                                                                                                                                                 |
| **매개변수**                 | `lst: 삭제할 요소`<br>`del: content 삭제에 사용되는 주소`                                                                                                                                                                                                                                                                                             |
| **반환값**                   | `없음`                                                                                                                                                                                                                                                                                                                                                            |
| **사용가능한 <br>외부 함수** | `free`                                                                                                                                                                                                                                                                                                                                                            |
| **설명**                     | _Takes as a parameter an element and frees the memory of the element’s content using the function ’del’ given as a parameter and free the element. The memory of ’next’ must not be freed._ <br> `첫 번째 인자값으로 받은 요소의 content를 두 번째 인자로 받은 함수 포인터를 이용해 해제하고, 요소 자체의 메모리를 해제합니다. next 포인터는 해제하면 안 됩니다.` |

<br>

| **함수 이름**                | ft_lstclear                                                                                                                                                                                                                                                                                                                                                 |
| ---------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **프로토타입**               | `void ft_lstclear(t_list **lst, void (*del)(void *));`                                                                                                                                                                                                                                                                                                      |
| **제출할 파일**              | -                                                                                                                                                                                                                                                                                                                                                           |
| **매개변수**                 | `lst: 삭제할 요소의 포인터`<br>`del: 요소의 content 삭제에 사용되는 함수 포인터`                                                                                                                                                                                                                                                                              |
| **반환값**                   | `없음`                                                                                                                                                                                                                                                                                                                                                      |
| **사용가능한 <br>외부 함수** | `free`                                                                                                                                                                                                                                                                                                                                                      |
| **설명**                     | _Deletes and frees the given element and every successor of that element, using the function ’del’ and free(3). Finally, the pointer to the list must be set to NULL._ <br> `함수 'del' 과 free(3) 을 이용하여 인자값으로 받은 요소와 그 뒤에 따라오는 리스트의 모든 요소들을 삭제하고 해제합니다. 마지막으로, 리스트의 포인터는 NULL로 설정되어야 합니다.` |

<br>

| **함수 이름**                | ft_lstiter                                                                                                                                                                                          |
| ---------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **프로토타입**               | `void ft_lstiter(t_list *lst, void (*f)(void *));`                                                                                                                                                  |
| **제출할 파일**              | -                                                                                                                                                                                                   |
| **매개변수**                 | `lst: 리스트상의 요소`<br>`f: 리스트 내에서 반복 적용될 함수 포인터`                                                                                                                                |
| **반환값**                   | `없음`                                                                                                                                                                                              |
| **사용가능한 <br>외부 함수** | `없음`                                                                                                                                                                                              |
| **설명**                     | _Iterates the list ’lst’ and applies the function ’f’ to the content of each element._ <br> `리스트 'lst' 를 순회하며, 리스트에 포함된 모든 요소들의 content에 함수 'f'를 반복적으로 적용시킵니다.` |

<br>

| **함수 이름**                | ft_lstmap                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| ---------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **프로토타입**               | `t_list *ft_lstmap(t_list *lst, void *(*f)(void *), void (*del)(void *));`                                                                                                                                                                                                                                                                                                                                                                                                                          |
| **제출할 파일**              | -                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| **매개변수**                 | `lst: 리스트상의 요소`<br>`f: 리스트 내에서 반복 적용될 함수 포인터`<br>`del: 필요할 경우, 요소의 content를 삭제하는 데에 사용되는 함수`                                                                                                                                                                                                                                                                                                                                                             |
| **반환값**                   | `새로운 리스트. 할당 실패 시, NULL`                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| **사용가능한 <br>외부 함수** | `malloc, free`                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| **설명**                     | _Iterates the list ’lst’ and applies the function ’f’ to the content of each element. Creates a new list resulting of the successive applications of the function ’f’. The ’del’ function is used to delete the content of an element if needed._ <br> `리스트 'lst'의 요소들을 순회하며 각 요소의 content에 함수 'f'를 연속적으로 적용시킵니다. 또한 함수 'f'를 적용시킨 결과물들을 content로 담은 새로운 리스트를 생성합니다. 'del' 함수들은 필요 시 각 요소의 content를 삭제하는 데 사용됩니다.` |
