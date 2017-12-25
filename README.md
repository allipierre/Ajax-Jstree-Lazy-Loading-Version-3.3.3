# Apex Region Plugin
Ajax Jstree  Lazy Loading Plugin Version 3.3.3
This Jstree is the new Version for https://github.com/tompetrus/oracle-apex-ajax-tree


# How to Use
1. Create a Region
2. Choose Type "Ajax Jstree Region Version 3.3.3 [Plug-In]"
3. SQL Query Example

```
select connect_by_isleaf as isleaf,
        level,
        TASK_NAME as name,
        'fa fa-folder' as icon,
        id as node_id,
        --TASK_NAME as tooltip,
        null  as link ,
         PARENT_TASK               parent_id, 
        ''             node_path 
   from EBA_UT_CHART_TASKS
   connect by prior id = PARENT_TASK
  start with parent_task is null
  order siblings by name 

```


```
SELECT LEVEL             ,
 mgr     parent_id, 
 empno             node_id, 
 ename             name, 
 connect_by_isleaf isleaf,
 ''             node_path ,
 'empno'             LINK ,
 'fa fa-home'   icon
                            
FROM   EMP_ 
CONNECT BY PRIOR empno = mgr 
START WITH mgr IS NULL 
ORDER  SIBLINGS BY ename

```

4. Under Attributes: - you can select the Options :

- Selected Node Id Item

- Search Node

- contextmenu                                        
                                        
- drag and drop                                   
                                        
                                        

# Preview

![](https://github.com/allipierre/Ajax-Jstree-Lazy-Loading-Version-3.3.3/blob/master/jstreeplugin.png)
