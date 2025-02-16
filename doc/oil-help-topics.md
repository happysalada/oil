---
in_progress: yes
css_files: ../web/base.css ../web/help-index.css ../web/toc.css
---

Oil Help Topics
===============

This is the online help for the Oil language.  It underlies the `help` builtin.

For example, typing `help proc` in the shell shows you how to use the `proc`
statement.  A link to this same text appears in the [`command`](#command)
**group** below.

To view this index inside the shell, use:

    help oil

An <span style="color: darkred">X</span> next to a help topic means that the
feature is **unimplemented**.

You may also want to browse [OSH Help Topics](osh-help-topics.html).

<div id="toc">
</div>

<h2 id="overview">
  Overview (<a class="group-link" href="oil-help.html#overview">overview</a>)
</h2>

```oil-help-topics
  [Usage]         bundle-usage   oil-usage
  [Oil Lexing]    docstring ###   X single-command ...
```

<h2 id="command">
  Command Language (<a class="group-link" href="oil-help.html#command">command</a>)
</h2>

```oil-help-topics
                  proc          proc p (x, y, @rest, &block) { echo hi }
                  equal =       = 1 + 2*3
                  underscore _  _ mylist.append(42)
                  oil-block     cd /tmp { echo $PWD }
```

<h2 id="assign">
  Assignments and Expression Language (<a class="group-link" href="oil-help.html#assign">assign</a>)
</h2>

```oil-help-topics
  [Keywords]      const   var   setvar   setglobal   setref
  [Literals]      oil-numbers    42  3.14  1e100
                  oil-string    r'[a-z]\n'  $'line\n'  
                  char-literal  #'a'   #'_'   \n   \\   \u{3bc}
                  bool-literal  True   False   None
                  list-literal  %(one two)  ['one', 'two', 3]
                  dict-literal  {name: 'bob'}
  [Operators]     concat        s1 ++ s2,  L1 ++ L2
                  oil-equals    ==   !=   ~==   is, is not, in, not in
                  oil-compare   <  <=  >  >=  (numbers only)
                  oil-logical    not  and  or
                  oil-arith     +  -  *  /  //  %   ** 
                  oil-bitwise   ~  &  |  ^  <<  >>
                  oil-ternary   '+' if x >= 0 else '-'
                  oil-index     a[3]  s[3]
                  oil-slice     a[1:-1]  s[1:-1]
                  func-call     f(x, y)
                  block-expr    &(echo $PWD)
                  builtin-sub   ${.myproc arg1}  @{.otherproc arg1}
                  match-ops     ~   !~   ~~   !~~
  [Eggex]         re-literal    / d+ /
                  re-compound   ~   (group)   <capture>   sequence
                  re-primitive  %zero   Subpattern   @subpattern
                                'sq'   "dq"   $x   ${x}
                  named-class    dot  digit  space  word  d  s  w
                  class-literal [c a-z 'abc' \\ \xFF \u0100]
                  X re-flags    ignorecase etc.
                  X re-multiline  ///
```

<h2 id="word">
  Word Language (<a class="group-link" href="oil-help.html#word">word</a>)
</h2>

```oil-help-topics
                  inline-call   $strfunc(x, y) @arrayfunc(z)
                  splice        @myarray @ARGV
                  expr-sub      echo $[42 + a[i]]
                  X oil-printf  ${x %.3f}
                  X oil-format  ${x|html}
```

<h2 id="builtin">
  Builtin Commands (<a class="group-link" href="oil-help.html#builtin">builtin</a>)
</h2>

```oil-help-topics
  [Oil Builtins]  oil-cd   oil-shopt     compatible, and takes a block
                  shvar                  Temporary modify global settings
                  push-registers         Save registers like $?, PIPESTATUS
                  fork   forkwait        Replace & and (), and takes a block
                  append                 Add elements to end of array
                  pp                     Pretty print interpreter state
                  write                  Like echo, but with --, -sep, -end
                  oil-read               Buffered I/O with --line, --all, --qsn
                  try                    Re-enable errexit; exit status utils
                  runproc                Run a proc; use as main entry point
                  module                 guard against duplicate 'source'
                  use                    change first word lookup
                  X fopen                Open multiple streams, takes a block
                  X argparse             getopts replacement, sets OPT
                  X log   X die          common functions (polyfill)
  [Data Formats]  json   X qtsv
X [External Lang] BEGIN   END   when (awk)
                  rule (make)   each (xargs)   fs (find)
X [Testing]       check
```

<h2 id="option">
  Shell Options (<a class="group-link" href="oil-help.html#option">option</a>)
</h2>

```oil-help-topics
  [Option Groups] strict:all   oil:basic   oil:all
  [Strictness]    ... More Runtime Errors
                  strict_argv            No empty argv
                  strict_arith           Fatal parse errors (on by default)
                  strict_array           Arrays don't decay to strings
                  strict_control_flow    Disallow misplaced keyword, empty arg
                  strict_errexit         Disallow code that ignores failure
                  strict_nameref         trap invalid variable names
                  strict_word_eval       Expose unicode and slicing errors
                  strict_tilde           Tilde subst can result in error
                  X strict_glob          Parse the sublanguage more strictly
  [Oil Basic]     ... Start Migrating to Oil
                  parse_at               echo @array @arrayfunc(x, y)
                  parse_brace            if true { ... }; cd ~/src { ... }
                  parse_paren            if (x > 0) ...
                  parse_raw_string       echo r'\' (command mode)
                  parse_triple_quote     """  '''  r'''  $''' in command mode
                  X parse_triple_dot     Multiline pipelines
                  command_sub_errexit    Synchronous errexit check
                  process_sub_fail       Analogous to pipefail for process subs
                  sigpipe_status_ok      status 141 -> 0 in pipelines
                  simple_word_eval       No splitting, static globbing
                  xtrace_rich            Hierarchical and process tracing
                  xtrace_details (-u)    Disable most tracing with +
                  dashglob (-u)          Disabled to avoid files like -rf
                  expand_aliases (-u)    Whether aliases are expanded
                  redefine_proc (-u)     Can procs be redefined?
  [Interactive]   redefine_module        'module' builtin always returns 0
                  X redefine_const       Can consts be redefined?
  [Simplicity]    ... More Consistent Style
                  simple_echo            echo takes 0 or 1 arguments
                  simple_eval_builtin    eval takes exactly 1 argument
                  simple_test_builtin    3 args or fewer; use test not [
                  X simple_trap          Function name only
  [Oil Breaking]  ... The Full Oil Language
                  X parse_amp            ls &2 > /dev/null, disallow >& <&
                  parse_at_all           @ starting any word is an operator
                  parse_equals           x = 'val' (for cleaner config blocks)
                  parse_backslash (-u)   Bad backslashes in $'' and c''
                  parse_backticks (-u)   Legacy syntax `echo hi`
                  parse_dollar (-u)      Is $ allowed for \$?  Maybe $/d+/
                  parse_ignored (-u)     Parse, but ignore, certain redirects
                  X copy_env (-u)        Use $[ENV->PYTHONPATH] when false
                  X old_builtins (-u)    local/declare/etc.  pushd/popd/dirs
                                         ... source  unset  printf  [un]alias
                                         ... getopts
                  X old_syntax (-u)      [[   $(( ))  ${x%prefix}   ${a[@]}
                                         $$
  [Compatibility] compat_array           ${array} is ${array[0]}
                  eval_unsafe_arith      Recursively parse and evaluate
                  parse_dynamic_arith    LHS can contain variables
                  verbose_errexit        Whether to print detailed errors
  [More Options]  allow_command_sub      For implementing strict_errexit
                  dynamic_scope          For implementing 'proc'
```

<h2 id="env">
  Environment Variables (<a class="group-link" href="oil-help.html#env">env</a>)
</h2>

```oil-help-topics
  [Oil Paths]     ?builtins   ?completion_plugins   ?coprocesses
```

<h2 id="special">
  Special Variables (<a class="group-link" href="oil-help.html#special">special</a>)
</h2>

```oil-help-topics
                  ARGV   ENV   OPT
  [Platform]      OIL_VERSION
  [Tracing]       SHX_indent   SHX_punct   SHX_pid_str
  [Shell Vars]    _ESCAPE   _DIALECT
  [Exit Status]   _status   _pipeline_status   _process_sub_status
X [Wok]           _filename   _line
X [Builtin Sub]   _buffer
```

<h2 id="lib">
  Builtin Functions (<a class="group-link" href="oil-help.html#lib">lib</a>)
</h2>

Access silently mutated globals:

```oil-help-topics
  [Pattern]       _match()   X _start()   X _end()
X [Wok]           _field()
```

Functions:

```oil-help-topics
  [Collections]   len()   copy()
X [String]        find()   sub()   join() 
                  split()             $IFS, awk algorithm, regex
  [Word]          glob()   maybe()
  [Arrays]        X index()   append()   extend()
  [Assoc Arrays]  @keys()   @values()
  [Introspection] shvar_get()
X [Config Gen]    block_to_str()   block_to_dict()   vm_eval()
X [Better Syntax] lstrip()   rstrip()   lstripglob()   rstripglob()
                  upper()   lower()
                  strftime()
X [Codecs]        posix-sh-str   oil-str   html-utf8
X [Hashing]       sha1   sha256 (etc.)
```
