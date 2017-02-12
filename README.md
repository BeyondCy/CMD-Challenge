# CMD-challenge

This repository contians *my* solutions to the [Commandline Challenge](https://cmdchallenge.com), a project to solve common tasks in one line bash commands.  Since possible solutions are already available on the [official GitHub repository](https://github.com/jarv/cmdchallenge) there is no harm in disclosing mine.

It's a great project and I encourage everyone to solve the tasks without looking at the solutions! If you do look, I hope you learn something. 

#### hello_world:
```bash
$ echo "hello world"
```

#### current_working_directory:
```bash
$ pwd
```

#### list_files:
```bash
$ dir
```

#### list_files_adv:
```bash
$ for f in $(ls -a); do if [ -d $f ] ; then echo $f/ ; elif [ -L $f ] ; then echo $f@ ; elif [ -x $f ] ; then echo $f"*"; else echo $f ; fi; done
```

#### nested_dirs:
```bash
$ cat .../\ \ /.\ .the\ flag.txt
```

#### print_file_contents:
```bash
$ cat access.log
```

#### last_lines:
```bash
$ tail -5 access.log
```

#### find_string_in_a_file:
```bash
$ grep "GET" access.log
```

#### find_tabs_in_a_file:
```bash
$ grep -P -c '\t' file-with-tabs.txt
```

#### search_for_files_containing_string:
```bash
$ grep -l 500 * 
```

#### search_for_files_by_extension:
```bash
$ find . -type f -iname "access.log*"
```

#### search_for_string_in_files_recursive:
```bash
$ find . -type f -iname "access.log*" -exec grep 500 {} \;
```

#### extract_ip_addresses:
```bash
$ find . -type f -iname "access.log*" -exec grep -Eo '[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}' {} \; 
```

#### delete_files:
```bash
$ rm -rfv * .*
```

#### count_files:
```bash
$ ls | wc -l
```

#### simple_sort:
```bash
$ cat access.log | sort
```

#### count_string_in_line:
```bash
$ grep GET access.log | wc -l
```

#### split_on_a_char:
```bash
$ cat split-me.txt | sed 's/;/\n/g'
```

#### print_number_sequence:
```bash
$ echo $(seq 1 100)
```

#### remove_files_with_a_dash:
```bash
$ find . -type f -iname "-*" -exec rm {} \;
```

#### remove_files_with_extension:
```bash
$ find . -type f -iname "*.doc" -exec rm {} \;
```

#### remove_files_without_extension:
```bash
$ find . -type f ! \( -name '*.exe' -o -name '*.txt' \) -exec rm {} \;
```

#### replace_text_in_files:
```bash
$ find . -type f -iname "*.txt" -exec sed -i 's/challenges are difficult//g' {} +
```

#### sum_all_numbers:
```bash
$ echo $(cat sum-me.txt) | sed 's/ /+/g' | bc
```

#### just_the_files:
```bash
$ find . -type f  -exec basename {} \;
```

#### remove_extensions_from_files:
```bash
$ for f in $(find . -type f); do mv $f ${f%*.*}; done
```

#### replace_spaces_in_filenames:
```bash
$ ls  | sed 's/ /./g'
```

#### files_starting_with_a_number
```bash
$ find . -type f -iname "[0-9]*" -exec basename {} \; 
```

#### print_nth_line:
```bash
$ head -25 faces.txt | tail -1
```

#### remove_duplicate_lines:
```bash
$ awk '!x[$0]++' faces.txt
```

#### corrupted_text:
```bash
$ cat war_and_peace.txt | sed 's/! !/ /g' | sed 's/sa!ve/save/g' | sed 's/ous!/ous/g' | sed 's/!.!/./g' | sed 's/!!thing/thing/g' | sed 's/he!/he/g' | sed 's/ll!/ll/g' | sed 's/ain..$/ain!/g'  | sed 's/!wi/wi/g'
```

#### print_common_lines:
```bash
$ for ip in $(grep -Eo '[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}' access.log.1); do grep $ip access.log.2| cut -d ' ' -f1; done   
```

