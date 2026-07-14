# MalbolgeLISP Quick Start

MalbolgeLISP is a LISP interpreter written in Malbolge — the most advanced Malbolge program ever created.

## Running MalbolgeLISP

You need a Malbolge interpreter. The original `malbolge.c` in this repo works:

```bash
gcc malbolge.c -o malbolge
./malbolge fast20.c   # fast interpreter
```

Wait for startup (can take several minutes on slow hardware — this is Malbolge). You will see a prompt.

## Basic REPL usage

MalbolgeLISP supports standard LISP syntax. A few examples:

```lisp
; Arithmetic
(+ 1 2)        ; => 3
(* 3 4)        ; => 12

; Define a variable
(def x 10)

; Lambda
((lambda (n) (* n n)) 5)   ; => 25

; Conditionals
(if (= x 10) (quote yes) (quote no))   ; => yes

; Lists
(cons 1 (cons 2 (cons 3 (quote ()))))  ; => (1 2 3)
(car (quote (a b c)))                  ; => a
(cdr (quote (a b c)))                  ; => (b c)
```

## Defining functions

```lisp
(defun square (n) (* n n))
(square 7)   ; => 49

(defun fact (n)
  (if (= n 0) 1 (* n (fact (- n 1)))))
(fact 5)     ; => 120
```

## Fibonacci example

```lisp
(defun fib (n)
  (if [n < 2] n
    (+ (fib (- n 1)) (fib (- n 2)))))
(fib 6)   ; => 8
```

## For more

Read the full manual in [MalbolgeLisp.pdf](./MalbolgeLisp.pdf) — written by the author during summer/fall 2021, it covers the full implementation including tacit programming, de Bruijn indices, and monad lifting.
