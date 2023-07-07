## HW_2 Postman

http://162.55.220.72:5005/first
1. Отправить запрос.
2. Статус код 200
```
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});
```
3. Проверить, что в body приходит правильный string.
```
pm.test("Body matches string", function () {
    pm.expect(pm.response.text()).to.include("This is the first responce from server!ss");
});
```
http://162.55.220.72:5005/user_info_3
1. Отправить запрос.
2. Статус код 200
```
pm.test("Статус код 200", function () {
    pm.response.to.have.status(200);
});
```
3. Спарсить response body в json.
```
var jsonData = pm.response.json();
```
4. Проверить, что name в ответе равно name s request (name вбить руками.)
```
pm.test("Проверить, что name в ответе равно name s request (name вбить руками.)", function () {
    pm.expect(jsonData.name).to.eql('Sergey');
});
```
5. Проверить, что age в ответе равно age s request (age вбить руками.)
```
pm.test("Проверить, что age в ответе равно age s request (age вбить руками.)", function () {
    pm.expect(jsonData.age).to.eql('32');
});
```
6. Проверить, что salary в ответе равно salary s request (salary вбить руками.)
```
pm.test("Проверить, что salary в ответе равно salary s request (salary вбить руками.)", function () {
    pm.expect(jsonData.salary).to.eql(1000);
});
```
7. Спарсить request.
```
var reqData = request.data
```
8. Проверить, что name в ответе равно name s request (name забрать из request.)
```
pm.test("Проверить, что name в ответе равно name s request (name забрать из request.)", function () {
    pm.expect(jsonData.name).to.eql(reqData.name);
});
```
9. Проверить, что age в ответе равно age s request (age забрать из request.)
```
pm.test("Проверить, что age в ответе равно age s request (age забрать из request.)", function () {
    pm.expect(jsonData.age).to.eql(reqData.age);
});
```
10. Проверить, что salary в ответе равно salary s request (salary забрать из request.)
```
pm.test("Проверить, что salary в ответе равно salary s request (salary забрать из request.)", function () {
    pm.expect(jsonData.salary).to.eql(parseInt(reqData.salary));
});
```
11. Вывести в консоль параметр family из response.
```
console.log(jsonData.family)
```
12. Проверить что u_salary_1_5_year в ответе равно salary*4 (salary забрать из request)
```
pm.test("Проверить что u_salary_1_5_year в ответе равно salary*4 (salary забрать из request)", function () {
    var respSalary_1_5_year = jsonData.family.u_salary_1_5_year
    pm.expect(parseInt(respSalary_1_5_year)).to.eql(reqData.salary*4);
});
```

http://162.55.220.72:5005/object_info_3
1. Отправить запрос.
2. Статус код 200
```
pm.test("Статус код 200", function () {
    pm.response.to.have.status(200);
});
```
3. Спарсить response body в json.
```
var jsonData = pm.response.json();
```
4. Спарсить request.
```
var reqData = pm.request.url.query.toObject()
```
5. Проверить, что name в ответе равно name s request (name забрать из request.)
```
pm.test("Проверить, что name в ответе равно name s request (name забрать из request.)", function () {
    pm.expect(jsonData.name).to.eql(reqData.name);
});
```
6. Проверить, что age в ответе равно age s request (age забрать из request.)
```
pm.test("Проверить, что age в ответе равно age s request (age забрать из request.)", function () {
    pm.expect(jsonData.age).to.eql(reqData.age);
});
```
7. Проверить, что salary в ответе равно salary s request (salary забрать из request.)
```
pm.test("Проверить, что salary в ответе равно salary s request (salary забрать из request.)", function () {
    pm.expect(jsonData.salary).to.eql(parseInt(reqData.salary)); 
});
```
8. Вывести в консоль параметр family из response.
```
console.log(jsonData.family)
```
9. Проверить, что у параметра dog есть параметры name
```
pm.test("Проверить, что у параметра dog есть параметры name", function () {
    pm.expect(jsonData.family.pets.dog).to.have.property('name');
});
```
10. Проверить, что у параметра dog есть параметры age.
```
pm.test("Проверить, что у параметра dog есть параметры age.", function () {
    pm.expect(jsonData.family.pets.dog).to.have.property('age'); 
});
```
11. Проверить, что параметр name имеет значение Luky.
```
pm.test("Проверить, что параметр name имеет значение Luky.", function () {
    pm.expect(jsonData.family.pets.dog.name).eql("Luky"); 
});
```
12. Проверить, что параметр age имеет значение 4.
```
pm.test("Проверить, что параметр age имеет значение 4.", function () {
    pm.expect(jsonData.family.pets.dog.age).eql(4); 
});
```
http://162.55.220.72:5005/object_info_4
1. Отправить запрос.
2. Статус код 200
```
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});
```
3. Спарсить response body в json.
```
var resp = pm.response.json(); 
```
4. Спарсить request.
```
var req = pm.request.url.query.toObject()
```
5. Проверить, что name в ответе равно name s request (name забрать из request.)
```
pm.test("Проверить, что name в ответе равно name s request (name забрать из request.)", function () {
    pm.expect(resp.name).to.eql(req.name);
});
```
6. Проверить, что age в ответе равно age s request (age забрать из request.)
```
pm.test("Проверить, что age в ответе равно age s request (age забрать из request.)", function () {
    pm.expect(resp.age).to.eql(parseInt(req.age));
});
```
7. Вывести в консоль параметр salary из request.
```
console.log(req.salary);
```
8. Вывести в консоль параметр salary из response.
```
console.log(resp.salary);
```
9. Вывести в консоль 0-й элемент параметра salary из response.
```
console.log(resp.salary[0]);
```
10. Вывести в консоль 1-й элемент параметра salary параметр salary из response.
```
console.log(resp.salary[1]);
```
11. Вывести в консоль 2-й элемент параметра salary параметр salary из response.
```
console.log(resp.salary[2]);
```
12. Проверить, что 0-й элемент параметра salary равен salary из request (salary забрать из request.)
```
pm.test("Проверить, что 0-й элемент параметра salary равен salary из request (salary забрать из request.))", function () {
    pm.expect(resp.salary[0]).to.eql(parseInt(req.salary));
});
```
13. Проверить, что 1-й элемент параметра salary равен salary*2 из request (salary забрать из request.)
```
pm.test("Проверить, что 1-й элемент параметра salary равен salary*2 из request (salary забрать из request.)", function () {
    pm.expect(parseInt(resp.salary[1])).to.eql(req.salary*2);
});
```
14. Проверить, что 2-й элемент параметра salary равен salary*3 из request (salary забрать из request.)
```
pm.test("Проверить, что 2-й элемент параметра salary равен salary*3 из request (salary забрать из request.)", function () {
    pm.expect(parseInt(resp.salary[2])).to.eql(req.salary*3);
});
```
15. Создать в окружении переменную name
16. Создать в окружении переменную age
17. Создать в окружении переменную salary
18. Передать в окружение переменную name
```
pm.environment.set("name", resp.name);
```
19. Передать в окружение переменную age
```
pm.environment.set("age", resp.age);
```
20. Передать в окружение переменную salary
```
pm.environment.set("salary", resp.salary[0]);
```
21. Написать цикл который выведет в консоль по порядку элементы списка из параметра salary.
```
for (let i = 0; i < resp.salary.length; i++) {
    console.log(resp.salary[i]);
};
```
---------
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});

var resp = pm.response.json(); //Спарсить response body в json.
var req = request.data //Спарсить request.

//Проверить, что json response имеет параметр start_qa_salary
pm.test("Проверить, что json response имеет параметр start_qa_salary", function () {
    pm.expect(resp).to.have.property('start_qa_salary'); 
});
//Проверить, что json response имеет параметр qa_salary_after_6_months
pm.test("Проверить, что json response имеет параметр qa_salary_after_6_months", function () {
    pm.expect(resp).to.have.property('qa_salary_after_6_months'); 
});
//Проверить, что json response имеет параметр qa_salary_after_12_months
pm.test("Проверить, что json response имеет параметр qa_salary_after_12_months", function () {
    pm.expect(resp).to.have.property('qa_salary_after_12_months'); 
});
//Проверить, что json response имеет параметр qa_salary_after_1.5_year
pm.test("Проверить, что json response имеет параметр qa_salary_after_1.5_year", function () {
    pm.expect(resp).to.have.property('qa_salary_after_1.5_year'); 
});
//Проверить, что json response имеет параметр qa_salary_after_3.5_years
pm.test("Проверить, что json response имеет параметр qa_salary_after_3.5_years", function () {
    pm.expect(resp).to.have.property('qa_salary_after_3.5_years'); 
});
//Проверить, что json response имеет параметр person
pm.test("Проверить, что json response имеет параметр person", function () {
    pm.expect(resp).to.have.property('person'); 
});
console.log(+req.salary);
//Проверить, что параметр start_qa_salary равен salary из request (salary забрать из request.)
pm.test("Проверить, что параметр start_qa_salary равен salary из request (salary забрать из request.)", function () {
    pm.expect(resp.start_qa_salary).to.eql(Number(req.salary));
});
//Проверить, что параметр qa_salary_after_6_months равен salary*2 из request (salary забрать из request.)
pm.test("Проверить, что параметр qa_salary_after_6_months равен salary*2 из request (salary забрать из request.)", function () {
    pm.expect(resp.qa_salary_after_6_months).to.eql(req.salary*2);
});
//Проверить, что параметр qa_salary_after_12_months равен salary*2.7 из request (salary забрать из request.)
pm.test("Проверить, что параметр qa_salary_after_12_months равен salary*2.7 из request (salary забрать из request.)", function () {
    pm.expect(resp.qa_salary_after_12_months).to.eql(req.salary*2.7);
});
//Проверить, что параметр qa_salary_after_1.5_year равен salary*3.3 из request (salary забрать из request.)
pm.test("Проверить, что параметр qa_salary_after_1.5_year равен salary*3.3 из request (salary забрать из request.)", function () {
    pm.expect(resp['qa_salary_after_1.5_year']).to.eql(req.salary*3.3);
});
//Проверить, что параметр qa_salary_after_3.5_years равен salary*3.8 из request (salary забрать из request.)
pm.test("Проверить, что параметр qa_salary_after_3.5_years равен salary*3.8 из request (salary забрать из request.)", function () {
    pm.expect(resp['qa_salary_after_3.5_years']).to.eql(req.salary*3.8);
});
//Проверить, что в параметре person, 1-й элемент из u_name равен salary из request (salary забрать из request.)
pm.test("Проверить, что в параметре person, 1-й элемент из u_name равен salary из request (salary забрать из request.)", function () {
    pm.expect(resp.person.u_name[1]).to.eql(Number(req.salary));
});
//Проверить, что что параметр u_age равен age из request (age забрать из request.)
pm.test("Проверить, что что параметр u_age равен age из request (age забрать из request.)", function () {
    pm.expect(resp.person.u_age).to.eql(Number(req.age));
});
//Проверить, что параметр u_salary_5_years равен salary*4.2 из request (salary забрать из request.)
pm.test("Проверить, что параметр u_salary_5_years равен salary*4.2 из request (salary забрать из request.)", function () {
    pm.expect(resp.person.u_salary_5_years).to.eql(req.salary*4.2);
});
//***Написать цикл который выведет в консоль по порядку элементы списка из параметра person.
for (key in resp.person) {
    console.log(key, resp.person[key]);
};


