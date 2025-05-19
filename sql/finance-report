select
	pl_date, 'Sales Order' as channel,
	sum(qty_order * price) as total_sales
from
	public.ufd_sales
group by
	1, 2

union all

select
	pl_date, 'Sales Order' as channel,
	sum(-qty * price) as total_sales
from
	public.ufd_sales_return
group by
	1, 2

union all

select
	cast(inv_date as date) as inv_date,
	'POS Sales' as channel, sum(qty * price) as total_sales
from
	public.ufd_pos_sales
group by
	1, 2

union all

select
	cast(inv_date as date) as inv_date,
	'POS Sales' as channel, sum(-qty * price) as total_sales
from
	public.ufd_pos_ret
group by
	1, 2

order by
	pl_date asc
