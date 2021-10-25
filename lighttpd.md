Regular Expressions

    Patterns ("wildcards") are matched against a string
    Special characters (see [http://www.regular-expressions.info/reference.html] for reference):

    . (full stop) - match any character
    * (asterisk) - match zero or more of the previous symbol
    + (plus) - match one or more of the previous symbol
    ? (question) - match zero or one of the previous symbol
    \? (backslash-something) - match special characters
    ^ (caret) - match the start of a string
    $ (dollar) - match the end of a string
    [set] - match any one of the symbols inside the square braces.
    [^set] - match any symbol that is NOT inside the square braces.
    (pattern) - grouping, remember what the pattern matched as a special variable
    {n,m} - from n to m times matching the previous character (m could be omitted to mean >=n times)
    (?!expression) - match anything BUT expression at the current position. Example: "^(/(?!(favicon.ico$|js/|images/)).*)" => "/fcgi/$1"

    Normal alphanumeric characters are treated as normal




Replacement Patterns

If the matched regex contains groups in parentheses, $1..$9 in the replacement refer to the captured text in the
matching group "$1" meaning the first group, "$2" the second, and so on.

Note that % replacements (like %1, %2, %0, etc.) in url.rewrite-* targets are permitted, but do not have the meaning they would have in evhost.path-pattern. If url.rewrite-* is specified within a regex conditional, % patterns are replaced by the corresponding groups from the condition regex. %1 is replaced with the first subexpression, %2 with the second, etc. %0 is replaced by the entire substring matching the regexp. See below for an example using "%0".
Extended Replacement Patterns¶

lighttpd provides ways to encode redirect and rewrite backreference substitutions (since 1.4.50) in curly-braces %{...} or ${...}

Up to nine (9) matches are saved for %{1} - %{9}. Up to nineteen (19) matches are saved for ${1} - ${19}.

In addition to %1 and $1, the following modifiers are now supported, followed by the number for the backreference, e.g. ${esc:1}.

    ${noesc:...} no escaping
    ${esc:...} escape all non-alphanumeric - . _ ~ incl double-escape %
    ${escape:...} escape all non-alphanumeric - . _ ~ incl double-escape %
    ${escnde:...} escape all non-alphanumeric - . _ ~ but no double-esc %
    ${escpsnde:...} escape all non-alphanumeric - . _ ~ / but no double-esc % (preserves literal /)
    ${tolower:...}
    ${toupper:...}
    ${encb64u:...} encode to base64url characters (no-padding)
    ${decb64u:...} decode from base64url characters

    %{noesc:...}
    %{esc:...}
    %{escape:...}
    %{escnde:...}
    %{escpsnde:...}
    %{tolower:...}
    %{toupper:...}
    %{encb64u:...}
    %{decb64u:...}

lighttpd provides ways to substitute URI parts without needing a regex match (since 1.4.50) (and can be preceded by encoding modifier, e.g. ${tolower:url.authority})

    ${url.scheme}
    ${url.authority}
    ${url.port}
    ${url.path}
    ${url.query}

    ${qsa} appends query string, if not empty
