# Popova Evgeniya
### Web Programmer
********* 
### Contact
- City: Tambov
- Phone: 89537070781
- E-mail: zeny0098@yandex.ru
- Telegram: @evgesha_it
********* 
### Skills
- HTML5
- CSS3
- PHP 7.x
- SQL
- JavaScript Basics
- Git
- Adobe Photoshop
- Gulp, YFM docs
- Editors: Sublime, notepad++, PhpStorm 2022
********* 
### Education
- Tambov State Technical University, Faculty of Information Technology, Information Systems and Technologies
********* 
### Experience
- 01.02.17 - 05.07.17. Company: It-technology. Profession: Web developer. Responsibilities: Creation and modification of websites.
- 01.09.17 - 14.09.18. Company: Demis Group. Profession: Tester. Responsibilities: Manual testing of sites, monitoring corrections, writing checklists, checking layout, functionality, SQL injections, loading speed, cross-browser compatibility, adaptive.
- 15.09.18 - 01.10.19. Company: Demis Group. Profession: Website technical support programmer. Responsibilities: Monitoring sites, editing content, improving/fixing functionality, installing and configuring modules, layout of contextual blocks/pages, and much more.
- 02.10.19 - 19.06.20. Company: Arbat-Service. Profession: Software Engineer. Responsibilities: Working with 1C, configurator, finalizing processing to suit the current tasks of the company.
- 21.06.20 - 01.02.24. Company: Nadezhda-Farm. Profession: Programmer. Responsibilities: Support of company websites. Refinement/development of functionality. Integration with third-party services.
********* 
### Code example
```
$sql = "SELECT q.* FROM (
                    SELECT 
                        rownum rn,
                        t.ID_GOOD_FIRM, t.ID_GOOD, t.ID_FIRM, t.MFR2_ID, t.NAME_GOOD, t.NAME_GOOD_URL, t.IS_JNVLS, t.CATEGOR1, t.PCATEGOR1, t.CATEGOR2, t.PCATEGOR2, t.CATEGOR3, t.PCATEGOR3, t.TEMPERATURE, t.COUNTRY_NAME, t.FIRM_NAME, t.MFR2, t.DATE_BEST, t.IS_RECEPT, t.KEYWORD, t.EAN13, t.G80_ID, t.G81_ID, t.G80_NAME, t.G81_NAME, t.NAME_ILL,
                        p.katmans,
                        a.*, 
                        v.name_def
                    FROM  (SELECT ts.*, row_number() over (partition by ts.ID_GOOD_FIRM order by ts.DATE_BEST,ts.ID_GOOD_FIRM) as sqnum
                             FROM factory_hope.price_for_inetapt_joint ts 
                             where ts.num_price = 1
                           ) t
                         ,(
                           SELECT id_good, LISTAGG(id_katman, ',') WITHIN GROUP (order by id_katman) AS katmans
                             FROM factory_hope.V_KATMAN_GOODS
                            GROUP BY id_good 
                          )p
                         ,factory_hope.goods y
                         ,factory_hope.goods_def v
                         ,(
                              SELECT  atx.id_good atx_id_good
                              , atx.name_fv
                              , atx.name_fs
                              , atx.id21 name_age
                              , atx.id20 name_sugarless
                              , atx.id22 name_gomeopat
                              , atx.name_19 name_taste
                              , atx.NAME_MNN
                              , atx.CODE_ATX
                              , nvl(atx.name_dz, atx.name_13) doz_count
                                , atx.name_14 doz_name
                                , CASE WHEN atx.id_group IN (
                                              SELECT gr.ID_GROUP 
                                                FROM factory_hope.GOODS_GROUP gr 
                                               WHERE gr.ID_GROUP1 = 2
                                               ) 
                              THEN 1 ELSE 0 END MEDICAL
                              from factory_hope.goods_atx1_view atx
                         ) a
                    WHERE 1=1 
                      AND t.sqnum = 1    
                      AND t.id_good = p.id_good
                      AND t.id_good = y.id_good
                      AND v.id_good_def = y.id_good_def
                      AND a.atx_id_good(+) = t.id_good
		        ) q WHERE rn between :vfrom and :vto";

        $rows = $os->getall($sql,[':vfrom'=>$row_from,':vto'=>$row_to]);
```
********* 
### Languages
- Russian: Native
- English: A1 (reading technical documentation)
