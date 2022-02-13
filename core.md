# Table of Contents



(ns scratch.core)

(defn foo  "I don't do a whole lot."
  [x]
  (println x "Hello, World!"))

(let [person "broseph"
      num-cats 186]
  (str person " has " num-cats "cats"))

(let [cats 3
      legs (\* 4 cats)]
  legs)

(foo "matej")

(let [burrito #(list "beans" % "cheese")]
  (burrito "carnitas"))
("beans" "carnitas" "cheese")

(let [twice (fn [x] (\* 2 x))]
  (+ (twice 1)
     (twice 3)))

(defn half
  ([] 1/2)
  ([x] (/ x 2)))

(half 5)

(defn add
  [x y]
  (+ x y))

(defn vargs
  [x y & more-args]
  {:x x
   :y y
   :more (fst more-args)}
  )

(vargs 1 2 3 4 5)

(defn launch
  "Launches a spacecraft into the given orbit by initiating a
  controlled on-axis burn. Does not automatically stage,
  but does vector thrust, if the craft supports it"
  [craft target-orbit]
  "Ok, we don't know how to control spacecraft yet.")

(meta #'launch)

(doc launch)

(seq [(inc (nth numbers 0)) (inc (nth numbers 1)) (inc (nth numbers 2))])

(defn inc-first [nums]
  (if (first nums)
    (cons (inc (first nums))
          (rest nums))
    (list)))

(defn inc-more [nums]
  (if (first nums)
    (cons (inc (first nums))
          (inc-more (rest nums)))
    (list)))

(def inc-first-fn (fn [nums]
                 (cons (inc (first nums))
                       (rest nums))))

(defn transform-all [f xs]
  (if (first xs)
    (cons (f (first xs))
          (transform-all f (rest xs)))
    (list)))

(inc-first [5])
(inc-first [])
(inc-more [1 2 3 4 5])
(transform-all list [1 2 3 4 5])
