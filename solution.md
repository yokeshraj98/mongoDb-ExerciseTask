Q1: Find all the information about each products

Ans:db.products.find();

Q2: Find the product price which are between 400 to 800

Ans: db.products.find({ product_price: { $gte: 400, $lte: 800 } });

Q3: Find the product price which are not between 400 to 600

Ans: db.products.find({ product_price: { $not: { $gte: 400, $lte: 800 } } });

Q4: List the four product which are greater than 500 in price

Ans: db.products.find({ product_price: { $gte: 500 } }).limit(4);

Q5: Find the product name and product material of each product

Ans: db.products.find({}, { product_name: 1, product_material: 1 });

Q6: Find the product with a row id of 10

Ans: db.products.find({ id: "10" });

Q7:Find only the product name and product material

Ans: db.products.find({}, { product_name:1, product_material:1});

Q8: Find all products which contain the value of soft in product material

Ans: db.products.find({ product_material: { $regex: /soft/, $options: "i" } });

Q9: Find products which contain product color indigo and product price 492.00

Ans: db.products.find({
  $and: [{ product_color: "indigo" }, { product_price: 492.0 }]
});

Q10: Delete the products which product price value are same

Ans: db.products.delete({ product_price: 500 });
