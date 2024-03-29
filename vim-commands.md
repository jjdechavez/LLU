### Make sure to install vim

`sudo apt-get install vim`

### Commands of Vim

1. To execute commands of vim - Esc
2. Insert/type data - i
3. arrow keys - up(k), down(j), left(h), right(l)
4. exit on vim - :q
   - exit with save - :wq
   - exit without saving - :q!
5. save file - :w
6. delete line - dd
7. down of the file - G
8. go back to top file - gg
9. undo the delete line - u
10. specify number jump - 10 down(j)
11. back the changes - ctrl + r
12. contious delete - dd then press .
13. copy paste - copy(yy) paste(p) for paste below, paste(P) for paste above
14. Visual mode or Hightlight - V
15. Insert empty line - below(o) above(O)
16. move across to the word - w
17. move back across to prev word - b
18. show the number of line - :number-of-line (:10 + enter)
19. cursor to display on the line - 0
20. cursor of the beginning of the line - ^
21. cursor of the last of the line - $
22. change specific then inser mode - c t j(want to remove)
23. delete specific character - d t /(character)
24. search with specific word - \*(must cursor on the word inorder to search)
25. focus on specific character - t
26. next to instance - ;
27. move view on the middle - zz
28. insert before the text - a
29. insert mode on the last line code - A
30. delete based on the cursor - x
31. inser mode on beginning line - I
32. to lowercase - ~
33. read last thing you do or command - .
34. replace depend the cursor - r
35. check the end based on the character - %

### Moving windows / multiple windows

- Ctrl W + L - Move the current window to the "far right"
- Ctrl W + H - Move the current window to the "far left"
- Ctrl W + J - Move the current window to the "very bottom"
- Ctrl W + K - Move the current window to the "very top"

Check out :help window-moving for more information

### Resize split window

- :res 50(width) - Resize vertical base on
- :vertical res 50 - Resize horizontal

### git/fugitive

- :Git (or just :G), which calls any arbitrary Git command.
- :G add
- :G commit

### Search and replace

For example, to search for the first occurrence of the string ‘foo’ in the current line and replace it with ‘bar’, you would use:
`:s/foo/bar/`

To replace all occurrences of the search pattern in the current line, add the g flag:
`:s/foo/bar/g`

If you want to search and replace the pattern in the entire file, use the percentage character % as a range.
This character indicates a range from the first to the last line of the file:
`:%s/foo/bar/g`

Main used commands

1. w
2. b
3. t /(specific character)
4. zz
5. a and A
6. I
7. ~ (turn the opposite letterseCase)
8. .
9. % d %
10. V y pp - copy & paste based on highlight
11. v t c

For Reference:
https://www.youtube.com/watch?v=IiwGbcd8S7I
