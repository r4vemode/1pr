# 1pr
-- 1)Используя таблицу hr.employees, hr.departments 
-- Выведите имя менеджера каждого департмента и его зарплату

    select t1.first_name,
    
    t1.salary
    
    from hr.employees t1

    join hr.departments t2

    on t1.employee_id = t2.MANAGER_ID;


-- 2) Используя таблицы oe.orders, oe.customers и hr.employees
-- Вывести имена покупателей и продавцов, которые сделали заказ, где статус заказа имеет значение 3


    select 
      t1.CUST_FIRST_NAME,
      t3.first_name,
      t2.order_status
    from oe.customers t1
    join oe.orders t2
    on t1.CUSTOMER_ID = t2.CUSTOMER_ID
    and t2.ORDER_STATUS = 3
    join hr.employees t3
    on t2.SALES_REP_ID = t3.employee_id;



-- 3)Используя таблицу hr.employees, hr.departments и hr.locations
-- Вывести имена сотрудников, чей департмент находится в провинции штата 'Техасс'

    select * from hr.employees;
    select * from hr.departments;
    select * from hr.locations;

    select 
        t3.first_name
    from hr.departments t1
    join hr.locations t2
    on t1.LOCATION_ID = t2.LOCATION_ID
    and t2.STATE_PROVINCE = 'Texas'
    join hr.employees t3
    on t1.DEPARTMENT_ID = t3.DEPARTMENT_ID;
