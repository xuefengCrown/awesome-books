

(+ (* 4 4) (* 3 3))

### 2.1.1 Function Application and Currying
所有过程都只有一个参数！
(+ 3 4)--> ((+ 3) 4)
(+ 3) 应该返回一个过程

### 2.1.2 括号的使用
多余的括号使得语义更加清晰

((+ 3) 4)
by establishing the convention that *function application associate to the left*(左结合)
we can write the expression more simply as: (+ 3 4)

((f ((+ 3) 4)) (g x))--> (f (+ 3 4) (g x))

### 2.1.3 built-in functions and constants
+,-,*,/
0,1,2,...
True, False
nil (the empty list)
if

复合数据构造, cons
(car (cons a b)) --> a
(cdr (cons a b)) --> (b)

### 2.1.4 the lambda abstractions 

(λ (x) (+ x 1))
(λ x . + x 1)

consists of: the λ, the formal parameter, the body

## 2.2 operational semantic of λ calculus
### 2.2.1 Bound and Free variable

(λ x . E) ;; 如何确定哪些x要被替换呢?
those occurrences of x which are free in E

      cons = (λa.λb.λf.f a b)
      head = (λc.c (λa.λb.a))
      tail = (λc.c (λa.λb.b))

      (define xcons (lambda (a) (lambda (b) (lambda (f) ((f a) b)))))		
      (define xhead (lambda (c) (c (lambda (a) (lambda (b) a)))))
      (define xtail (lambda (c) (c (lambda (a) (lambda (b) b)))))	

      (define p ((xcons 1) 2))




























