# column

> Format `stdin` or a file into multiple columns.
> Columns are filled before rows; the default separator is a whitespace.
> More information: <https://keith.github.io/xcode-man-pages/column.1.html>.

- Format the output of a command for a 30 characters wide display:

`printf "header1 header2\nbar foo\n" | column -c {{30}}`

- Split columns automatically and auto-align them in a tabular format:

`printf "header1 header2\nbar foo\n" | column -t`

- Specify the column delimiter character for the `-t` option (e.g. "," for CSV) (defaults to whitespace):

`printf "header1,header2\nbar,foo\n" | column -t -s {{,}}`

- Fill rows before filling columns:

`printf "header1\nbar\nfoobar\n" | column -c {{30}} -x`

- Align colon-delimited file content (e.g. /etc/passwd):

`column -s ":" -t {{/etc/passwd}}`
