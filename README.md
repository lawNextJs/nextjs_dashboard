# Next.js App Router Course - Starter

This is the starter template for the Next.js App Router Course. It contains the starting code for the dashboard application.

For more information, see the [course curriculum](https://nextjs.org/learn) on the Next.js Website.

Vercel
<https://nextjs-dashboard-omega-five-86.vercel.app/>

current lesson
<https://nextjs.org/learn/dashboard-app/mutating-data>
<https://nextjs.org/learn/dashboard-app/error-handling>

attention lesson
<https://nextjs.org/learn/dashboard-app/partial-prerendering>

sample query (user name, invoice date, invoice status is 'paid')
select customers_list.name, status, date from invoices join (select name, id from customers) as customers_list on customers_list.id = customer_id and status = 'paid' order by customers_list.name

sample query (user name, amount)
select customers.name, amount from invoices join customers on customer_id = customers.id

sample query (user name, amount_sum)
select customers.name, sum(amount) from invoices join customers on customer_id = customers.id group by customers.name order by customers.name
(771, 202)ms

sample query (user name, amount_sum)
select customers.name, sum(amount) from invoices join (select id, name from customers) as customers on customer_id = customers.id group by customers.name order by customers.name
(782, 201)ms
서브쿼리를 사용하여 필요한 컬럼만 선택하고 있습니다. 따라서 customers 테이블의 크기에 비해 적은 데이터만을 메모리에 가져오게 되어 효율적입니다. 특히 customers 테이블이 작은 경우에는 더 효과적일 수 있습니다.
하지만 최적화는 많은 변수에 의존하며, 데이터베이스 엔진, 인덱스, 테이블 구조 등 여러 요소가 영향을 미칩니다. 성능을 평가하기 위해서는 실제 데이터베이스에서 실행 계획을 확인하고, 인덱스를 효과적으로 활용하는지 확인하는 것이 좋습니다. 데이터가 큰 경우에는 쿼리를 작성할 때 인덱스를 고려하여 최적화하도록 노력하는 것이 중요합니다.

terminal
    - zsh
    - ohmyzsh
      - theme
        - powerlevel10k
      - font
        - MesloLGS NF (recommended)
        - D2Coding ligature
      - plugin
        - zsh-autosuggestions
        - Syntax Highlighting
        - lsd

convention
    - 마지막에 `;` 사용하지 않음
    - `'` 우선 사용
      - console.log('hello') [O]
      - console.log("hello") [X]
    - tab size = 2
