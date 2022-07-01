
### http://162.55.220.72:5005/first
## 2. Статус код 200 

### pm.test('status code 200', function() {
###    pm.response.to.have.status(200);
### });

## 3. Проверить, что в body приходит правильный string.

### let respText = pm.response.text();

### pm.test('body = string', function() {
###     pm.expect(respText).to.include('This is the first responce from server!');
### });

-----------------

## // 2. Статус код 200

### pm.test('Status code 200', function() {
###     pm.response.to.have.status(200);
=======
### // 1. Отправить запрос.
## // 2. Статус код 20

## pm.test('Status code 200', function() {
##     pm.response.to.have.status(200);
### });

### // 3. Спарсить response body в json.
## let respJson = pm.response.json();

### // 4. Проверить, что name в ответе равно name s request (name вбить руками.)
## pm.test('Name в ответе равно name s request', function() {
##     pm.expect(respJson.name).to.eql('isma');
## });

### // 5. Проверить, что age в ответе равно age s request (age вбить руками.)
## pm.test('Age в ответе равно age s request', function() {
##     pm.expect(respJson.age).to.eql('30');
## });

### // 6. Проверить, что salary в ответе равно salary s request (salary вбить руками.)
## pm.test('Salary в ответе равно salary s request', function() {
##     pm.expect(respJson.salary).to.eql(1000);
## });

### // 7. Спарсить request.
## let reqJson = request.data;

### // 8. Проверить, что name в ответе равно name s request (name забрать из request.)
## pm.test('Test = name(req)', function() {
##     pm.expect(respJson.name).to.eql(reqJson.name);
## });

### // 9. Проверить, что age в ответе равно age s request (age забрать из request.)
## pm.test('Test = age(req)', function() {
##     pm.expect(respJson.age).to.eql(reqJson.age);
## });

### // 10. Проверить, что salary в ответе равно salary s request (salary забрать из request.)

## pm.test('salary = salary request1', function(){
##     pm.expect(respJson.salary).to.eql(+reqJson.salary);
## });

## pm.test('Test = salary(req)', function() {
##     pm.expect(respJson.salary).to.eql(parseInt(reqJson.salary));
### });


## // 3. Спарсить response body в json.

### let respJson = pm.response.json();


## // 4. Проверить, что name в ответе равно name s request (name вбить руками.)
### pm.test('Name в ответе равно name s request', function() {
###     pm.expect(respJson.name).to.eql('isma');
### });


## // 5. Проверить, что age в ответе равно age s request (age вбить руками.)
### pm.test('Age в ответе равно age s request', function() {
###     pm.expect(respJson.age).to.eql('30');
### });


## // 6. Проверить, что salary в ответе равно salary s request (salary вбить руками.)
### pm.test('Salary в ответе равно salary s request', function() {
###     pm.expect(respJson.salary).to.eql(1000);
### });


## // 7. Спарсить request.
### let reqJson = request.data;


## // 8. Проверить, что name в ответе равно name s request (name забрать из request.)
### pm.test('Test = name(req)', function() {
###     pm.expect(respJson.name).to.eql(reqJson.name);
### });


## // 9. Проверить, что age в ответе равно age s request (age забрать из request.)
### pm.test('Test = age(req)', function() {
###     pm.expect(respJson.age).to.eql(reqJson.age);
### });


## // 10. Проверить, что salary в ответе равно salary s request (salary забрать из request.)

### pm.test('salary = salary request1', function(){
###     pm.expect(respJson.salary).to.eql(+reqJson.salary);
### });

### OR

### pm.test('Test = salary(req)', function() {
###     pm.expect(respJson.salary).to.eql(parseInt(reqJson.salary));
### });


## // 11. Вывести в консоль параметр family из response.

### console.log('FamilyResp  ', respJson.family);


## // 12. Проверить что u_salary_1_5_year в ответе равно salary*4 (salary забрать из request)

### pm.test('u_salary_1_5_year в ответе равно salary*4(req)', function() {
###     pm.expect(respJson.family.u_salary_1_5_year).to.eql(reqJson.salary*4)
### });


------------------


### http://162.55.220.72:5005/object_info_3

## // 2. Статус код 200

### pm.test('Status code 200', function()  {
###     pm.response.to.have.status(200);
### });


## // 3. Спарсить response body в json.

### let respJson = pm.response.json();


## // 4. Спарсить request.

### let reqJson = pm.request.url.query.toObject();


## // 5. Проверить, что name в ответе равно name s request (name забрать из request.)

### pm.test('name в ответе равно name s request(req)', function() {
###     pm.expect(respJson.name).to.eql(reqJson.name);
### });


## // 6. Проверить, что age в ответе равно age s request (age забрать из request.)
### pm.test('age в ответе равно age s request(req', function() {
###     pm.expect(respJson.age).to.eql(reqJson.age);
### });

## // 7. Проверить, что salary в ответе равно salary s request (salary забрать из request.)
### pm.test('salary в ответе равно salary s request(req)', function() {
###     pm.expect(respJson.salary).to.eql(+reqJson.salary);
### });


## // 8. Вывести в консоль параметр family из response.
### console.log('FamilyResp', respJson.family);


## // 9. Проверить, что у параметра dog есть параметры name.
### // pm.test('dog есть параметры name', function() {
### //     pm.expect(respJson.family.pets.dog).not.eql('name')
### // });



### pm.test('dog есть параметры name', function() {
###     pm.expect(respJson.family.pets.dog).to.have.property('name')
### });


## // 10. Проверить, что у параметра dog есть параметры age.
### pm.test('dog есть параметры age', function() {
###     pm.expect(respJson.family.pets.dog).to.have.property('age');
### });


## // 11. Проверить, что параметр name имеет значение Luky.
### pm.test('параметр name имеет значение Luky', function() {
###     pm.expect(respJson.family.pets.dog.name).to.eql('Luky');
### });


## // 12. Проверить, что параметр age имеет значение 4.
### pm.test('dog есть параметры name', function() {
###     pm.expect(respJson.family.pets.dog.age).to.eql(4);
### });


-------------


### http://162.55.220.72:5005/object_info_4

## // 2. Статус код 200
### pm.test('status code 200', function() {
###     pm.response.to.have.status(200);
### });


## // 3. Спарсить response body в json.
### let respJson = pm.response.json()


## // 4. Спарсить request.
### let reqJson = pm.request.url.query.toObject();

## // 5. Проверить, что name в ответе равно name s request (name забрать из request.)
### pm.test('name в ответе равно name s request(req)', function() {
###     pm.expect(respJson.name).to.eql(reqJson.name)
### });


## // 6. Проверить, что age в ответе равно age из request (age забрать из request.)
### pm.test("age в ответе равно age из request(req)", function() {
###     pm.expect(respJson.age).to.eql(+reqJson.age);
### });


## // 7. Вывести в консоль параметр salary из request.
### console.log('SalaryReq', reqJson.salary);


## // 8. Вывести в консоль параметр salary из response.
### console.log('Salary.Resp', respJson.family);

## // 9. Вывести в консоль 0-й элемент параметра salary из response.
### console.log('0 element from salary', respJson.salary[0]);


## // 10. Вывести в консоль 1-й элемент параметра salary параметр salary из response.
### console.log('1 element from salary', respJson.salary[1]);


## // 11. Вывести в консоль 2-й элемент параметра salary параметр salary из response.
### console.log('2 element from salary', respJson.salary[2]);


## // 12. Проверить, что 0-й элемент параметра salary равен salary из request (salary забрать из request.)
### pm.test('0-й элемент параметра salary равен salary(req)', function() {
###     pm.expect(respJson.salary[0]).to.eql(+reqJson.salary);
### });


## // 13. Проверить, что 1-й элемент параметра salary равен salary*2 из request (salary забрать из request.)
### let reqSalary = parseInt(reqJson.salary*2);


### pm.test('1-й элемент параметра salary равен salary*2(req)', function() {
###     pm.expect(+respJson.salary[1]).to.eql(reqSalary);
### });


## // 14. Проверить, что 2-й элемент параметра salary равен salary*3 из request (salary забрать из request.)
### let reqSalary_1 = parseInt(reqJson.salary*3);


### pm.test('2-й элемент параметра salary равен salary*3(req)', function() {
###     pm.expect(+respJson.salary[2]).to.eql(reqSalary_1);
### });


## // 15. Создать в окружении переменную name
## // 16. Создать в окружении переменную name
### pm.environment.set('name', respJson.name);


## // 17. Создать в окружении переменную salary
## // 18. Передать в окружение переменную salary
### pm.environment.set('salary', respJson.salary[0]);


## // 19. Передать в окружение переменную age
## // 20. Передать в окружение переменную age
### pm.environment.set('age', respJson.age);


## // 21. Написать цикл который выведет в консоль по порядку элементы списка из параметра salary.

### let respSalary = respJson.salary;
### let Salary = [respSalary[0], respSalary[1], respSalary[2]];
	
### for (let i = 0; i < Salary.length; i++) {
### console.log(Salary[i])};
