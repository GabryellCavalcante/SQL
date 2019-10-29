SELECT DISTINCT

cd.NOME_DEV as NOME
,cdf.CONTRATO_FIN as CONTRATO
,cdf.VALOR_FIN as VALOR
,c.RAZAO_CLI as PRODUTO
,cdf.CPF_DEV as CPF
,cdf.DTENTRADA_FIN as ENTRADA

FROM CAD_DEVF cdf (NOLOCK)
left join cad_cli c WITH (NOLOCK) on c.cod_cli = cdf.cod_cli
left join cad_car cc WITH (NOLOCK) on (cc.cod_cli = cdf.cod_cli and cc.cod_car = cdf.cod_car)
left join CAD_DEV cd with (nolock) on cd.CPF_DEV = cdf.CPF_DEV

WHERE c.RAZAO_CLI IN ('LOSANGO DIGITAL', 'LOSANGO CDC')
and cdf.CPF_DEV != '0'
AND cdf.DTENTRADA_FIN BETWEEN '2019-10-01 00:00:00' AND '2019-10-31 00:00:00'

ORDER BY DTENTRADA_FIN DESC



/* ------------------------------------ */

SELECT DISTINCT

cd.NOME_DEV as NOME
,cdf.CONTRATO_FIN as CONTRATO
,cdf.VALOR_FIN as VALOR
,c.RAZAO_CLI as PRODUTO
,cdf.CPF_DEV as CPF
,cdf.DTENTRADA_FIN as ENTRADA
,cdf.ATRASO_FIN as ATRASO
,cdt.DDD_TEL as DDD
,cdt.TEL_TEL as TELEFONE
,cde.CIDADE_END as CIDADE
,cuf.DESC_UF as UF

FROM CAD_DEVF cdf WITH (NOLOCK)
left join cad_cli c WITH (NOLOCK) on c.cod_cli = cdf.cod_cli
left join cad_car cc WITH (NOLOCK) on (cc.cod_cli = cdf.cod_cli and cc.cod_car = cdf.cod_car)
left join cad_dev cd WITH (NOLOCK) on cd.CPF_DEV = cdf.CPF_DEV
left join cad_devt cdt WITH (NOLOCK) on cdt.CPF_DEV = cdf.CPF_DEV
left join cad_deve cde WITH (NOLOCK) on cde.CPF_DEV = cdf.CPF_DEV
left join cad_uf cuf WITH (NOLOCK) on cde.cod_uf = cuf.cod_uf

WHERE c.RAZAO_CLI IN ('LOSANGO DIGITAL', 'LOSANGO CDC')
AND cdf.CPF_DEV != '0'
AND cdf.DTENTRADA_FIN BETWEEN '2019-10-01 00:00:00' AND '2019-10-31 00:00:00'

ORDER BY cdf.ATRASO_FIN DESC
