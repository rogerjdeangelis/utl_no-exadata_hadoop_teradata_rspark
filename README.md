# utl_no-exadata_hadoop_teradata_rspark
Say no to exadata, hadoop, teradata and rspark. Use the free SPDE and workstation SAS. SAS on a power worstation with SPDE partitioning and parallel indexing.

    ```  Do you really need EXADATA, HADDOP, TERDATA or RSPARK if you have workstation SAS  ```
    ```    ```
    ```  Timings with and without SPDE on a workstation  ```
    ```    ```
    ```     1. 0.99 seconds (partitioned data with two idecies on a workstation with SPDE)  ```
    ```     2. 2.80 seconds (non partitioned data)  ```
    ```    ```
    ```  All data and code enclosed  ```
    ```    ```
    ```  SOFTWARE  ```
    ```  ========  ```
    ```    ```
    ```  1. SPDE on SAS Workstation(SAS prefers PC SAS)  35gb dataset partitioned in 0.5gb pieces  ```
    ```  2. SAS Workstation(SAS prefers PC SAS) 35gb not partitioned data  ```
    ```    ```
    ```  I expect the same extract from a  500gb data structures to take about the same time using SPDE.  ```
    ```    ```
    ```  Here is an example of partitioned data using multiple parallel index execution.  ```
    ```  Too lazy to work with big data (could take 1hr to build 500gb data structure)  ```
    ```    ```
    ```    ```
    ```  HAVE 35gb partitioed data with parallel indexing (640,000,000 million obs)  ```
    ```  =======================================================================  ```
    ```    ```
    ```  PARTITION DATA  ```
    ```  ==============  ```
    ```    ```
    ```  The CONTENTS Procedure  ```
    ```    ```
    ```  Data Set Name        SPDE.DT                       Observations          640,000,000  ```
    ```  Member Type          DATA                          Variables             7  ```
    ```  Engine               SPDE                          Indexes               2  ```
    ```  Created              10/07/2016 09:55:10           Observation Length    56  ```
    ```  Last Modified        10/07/2016 09:55:10           Deleted Observations  0  ```
    ```  Protection                                         Compressed            NO  ```
    ```  Data Set Type                                      Sorted                NO  ```
    ```    ```
    ```    ```
    ```       Engine/Host Dependent Information  ```
    ```    ```
    ```  Blocking Factor (obs/block)        18724  ```
    ```  Data Partsize                      524287232  ```
    ```  -   Alphabetic List of Index Info  -  ```
    ```  Index                              IDX  ```
    ```  KeyValue (Min)                     0  ```
    ```  KeyValue (Max)                     10000  ```
    ```  Number of discrete values          10001  ```
    ```  Index                              IDX2  ```
    ```  KeyValue (Min)                     0  ```
    ```  KeyValue (Max)                     1000  ```
    ```  Number of discrete values          1001  ```
    ```    ```
    ```         Variables in Creation Order  ```
    ```    ```
    ```  #    Variable    Type    Len    Informat  ```
    ```    ```
    ```  1    IDX         Num       8  ```
    ```  2    IDX2        Num       8  ```
    ```  3    A           Char      4    $4.  ```
    ```  4    B           Num       8  ```
    ```  5    D           Num       8  ```
    ```  6    E           Num       8  ```
    ```  7    F           Num       8  ```
    ```    ```
    ```    ```
    ```  Alphabetic List of Indexes and Attributes  ```
    ```    ```
    ```                  # of  ```
    ```                Unique  ```
    ```  #    Index    Values  ```
    ```    ```
    ```  1    IDX       10001  ```
    ```  2    IDX2       1001  ```
    ```    ```
    ```    ```
    ```  NON PARTITIONED  ```
    ```  ===============  ```
    ```    ```
    ```    ```
    ```  Data Set Name        INP.WRK_DT                    Observations          640,000,000  ```
    ```  Member Type          DATA                          Variables             7  ```
    ```  Engine               V9                            Indexes               2  ```
    ```  Created              10/07/2016 09:38:19           Observation Length    56  ```
    ```  Last Modified        10/07/2016 09:38:19           Deleted Observations  0  ```
    ```  Protection                                         Compressed            NO  ```
    ```  Data Set Type                                      Sorted                NO  ```
    ```  Label  ```
    ```  Data Representation  WINDOWS_64  ```
    ```  Encoding             wlatin1  Western (Windows)  ```
    ```    ```
    ```    ```
    ```          Engine/Host Dependent Information  ```
    ```    ```
    ```  Data Set Page Size          65536  ```
    ```  Number of Data Set Pages    548416  ```
    ```  First Data Page             1  ```
    ```  Max Obs per Page            1167  ```
    ```  Obs in First Data Page      1137  ```
    ```  Index File Page Size        32256  ```
    ```  Number of Index File Pages  319010  ```
    ```  Number of Data Set Repairs  0  ```
    ```  ExtendObsCounter            YES  ```
    ```  Filename                    e:\wrk\wrk_dt.sas7bdat  ```
    ```  Release Created             9.0401M2  ```
    ```  Host Created                X64_7PRO  ```
    ```    ```
    ```    ```
    ```  Alphabetic List of Variables and Attributes  ```
    ```    ```
    ```  #    Variable    Type    Len    Informat  ```
    ```    ```
    ```  3    A           Char      4    $4.  ```
    ```  4    B           Num       8  ```
    ```  5    D           Num       8  ```
    ```  6    E           Num       8  ```
    ```  7    F           Num       8  ```
    ```  1    IDX         Num       8  ```
    ```  2    IDX2        Num       8  ```
    ```    ```
    ```  The CONTENTS Procedure  ```
    ```    ```
    ```  Alphabetic List of Indexes and Attributes  ```
    ```    ```
    ```                  # of  ```
    ```                Unique  ```
    ```  #    Index    Values  ```
    ```    ```
    ```  1    IDX       10001  ```
    ```  2    IDX2       1001  ```
    ```    ```
    ```  WANT ( EXTRACT  records using the where clase below in less than 1 second )  ```
    ```    ```
    ```    ```
    ```  WHERE idx1 in  ```
    ```  (1000, 1010, 1020, 1030, 1040, 1050, 1060, 1070, 1080 ,  ```
    ```  1090, 1100, 1110, 1120, 1130, 1140, 1150, 1160, 1170, 1180, 1190 , 1200,  ```
    ```  1210, 1220, 1230, 1240, 1250, 1260, 1270, 1280, 1290, 1300, 1310, 1320,  ```
    ```  1330, 1340, 1350 , 1360, 1370, 1380, 1390, 1400, 1410, 1420, 1430, 1440,  ```
    ```  1450, 1460 , 1470, 1480, 1490, 1500, 1510, 1520, 1530, 1540, 1550, 1560,  ```
    ```  1570, 1580, 1590, 1600, 1610, 1620 , 1630, 1640, 1650, 1660, 1670, 1680,  ```
    ```  1690, 1700, 1710, 1720, 1730, 1740, 1750, 1760, 1770, 1780, 1790, 1800)  ```
    ```    ```
    ```   and idx2 in  ```
    ```  (100, 102, 104, 106, 108, 110, 112, 114, 116, 118, 120, 122,  ```
    ```  124, 126, 128, 130, 132, 134, 136, 138, 140, 142, 144, 146, 148, 150,  ```
    ```  152, 154, 156, 158, 160, 162, 164, 166, 168, 170, 172, 174, 176, 178,  ```
    ```  180, 182, 184, 186, 188, 190, 192, 194, 196, 198, 200, 202, 204, 206,  ```
    ```  208, 210, 212, 214, 216, 218, 220, 222, 224, 226, 228, 230, 232, 234,  ```
    ```  236, 238, 240, 242, 244, 246, 248, 250, 252, 254, 256, 258, 260)  ```
    ```    ```
    ```    ```
    ```  SOLUTION  ```
    ```    ```
    ```  * CREATE THE NON-PARTITIINED DATA;  ```
    ```    ```
    ```  * create the csv file using R from a previous post;  ```
    ```  %utl_submit_r64('  ```
    ```  library(data.table);  ```
    ```  n=1e7;  ```
    ```  DT = data.table(  ```
    ```                   a=sample(c("foo","bar","baz","qux","quux"),n,replace=TRUE),  ```
    ```                   b=sample(1:1000,n,replace=TRUE),  ```
    ```                   c=rnorm(n),  ```
    ```                   d=sample(1:1000,n,replace=TRUE),  ```
    ```                   e=rnorm(n),  ```
    ```                   f=sample(1:1000,n,replace=TRUE) );  ```
    ```  write.table(DT,"d:/csv/test.csv",sep=",",row.names=FALSE,quote=FALSE);  ```
    ```  partsize=2gb;  ```
    ```  ');  ```
    ```    ```
    ```  * CREATE THE NON PARTITIONED DATA( 35gb with two indexes);;  ```
    ```    ```
    ```  data wrk_dt(compress=no index=(idx idx2));  ```
    ```   retain idx idx2 0;  ```
    ```   informat a $4.;  ```
    ```   infile "d:/csv/test.csv" dlm=',' firstobs=2;  ```
    ```   input a b c d e f;  ```
    ```   if mod(_n_,1000)=0 then idx=idx+1;  ```
    ```   if mod(_n_,10000)=0 then idx2=idx2+1;  ```
    ```   do dup=1 to 64;  ```
    ```     output;  ```
    ```   end;  ```
    ```   drop dup c;  ```
    ```  run;quit;  ```
    ```    ```
    ```  * CREATE THE PARTITIINED DATA;  ```
    ```  * It took about half the time to create the  ```
    ```    equivalent partitiond data, not almost 4 theads/cores was used?  ```
    ```    ```
    ```    8:53 clock 30:53 CPU  ```
    ```    ```
    ```  libname spde spde  ```
    ```   ('c:\wrk\spde_c','d:\wrk\spde_d','e:\wrk\spde_e','g:\wrk\spde_g','h:\wrk\spde_h')  ```
    ```      metapath =('c:\wrk\spde_c\metadata')  ```
    ```      indexpath=(  ```
    ```            'c:\wrk\spde_c'  ```
    ```            ,'d:\wrk\spde_d'  ```
    ```            ,'e:\wrk\spde_e'  ```
    ```            ,'g:\wrk\spde_g'  ```
    ```            ,'h:\wrk\spde_h')  ```
    ```    ```
    ```      datapath =(  ```
    ```            'c:\wrk\spde_c'  ```
    ```            ,'d:\wrk\spde_d'  ```
    ```            ,'e:\wrk\spde_e'  ```
    ```            ,'g:\wrk\spde_g'  ```
    ```            ,'h:\wrk\spde_h')  ```
    ```      partsize=500m  ```
    ```  ;  ```
    ```    ```
    ```  data spde.dt(compress=no index=(idx idx2));  ```
    ```   retain idx idx2 0;  ```
    ```   informat a $4.;  ```
    ```   infile "d:/csv/test.csv" dlm=',' firstobs=2;  ```
    ```   input a b c d e f;  ```
    ```   if mod(_n_,1000)=0 then idx=idx+1;  ```
    ```   if mod(_n_,10000)=0 then idx2=idx2+1;  ```
    ```   do dup=1 to 64;  ```
    ```     output;  ```
    ```   end;  ```
    ```   drop dup c;  ```
    ```  run;quit;  ```
    ```    ```
    ```    ```
    ```  NOTE: The infile "d:/csv/test.csv" is:  ```
    ```        Filename=d:\csv\test.csv,  ```
    ```        RECFM=V,LRECL=32767,  ```
    ```        File Size (bytes)=531993311,  ```
    ```        Last Modified=05Oct2016:17:50:54,  ```
    ```        Create Time=05Oct2016:17:32:26  ```
    ```    ```
    ```  NOTE: 10,000,000 records were read from the infile "d:/csv/test.csv".  ```
    ```        The minimum record length was 42.  ```
    ```        The maximum record length was 59.  ```
    ```  NOTE: The data set SPDE.DT has 640,000,000 observations and 7 variables.  ```
    ```  NOTE: DATA statement used (Total process time):  ```
    ```        real time           8:53.69  ```
    ```        cpu time            30:52.55  ```
    ```    ```
    ```    ```
    ```  BATCH OUTPUT  ```
    ```    ```
    ```  UNPARTITION  ```
    ```    ```
    ```  NOTE: There were 2624000 observations read from the data set SPDE.DT.  ```
    ```  WHERE idx in (1000, 1010, 1020, 1030, 1040, 1050, 1060, 1070, 1080,  ```
    ```  1090, 1100, 1110, 1120, 1130, 1140, 1150, 1160, 1170, 1180, 1190, 1200,  ```
    ```  1210, 1220, 1230, 1240, 1250, 1260, 1270, 1280, 1290, 1300, 1310, 1320,  ```
    ```  1330, 1340, 1350, 1360, 1370, 1380, 1390, 1400, 1410, 1420, 1430, 1440,  ```
    ```  1450, 1460, 1470, 1480, 1490, 1500, 1510, 1520, 1530, 1540, 1550, 1560,  ```
    ```  1570, 1580, 1590, 1600, 1610, 1620, 1630, 1640, 1650, 1660, 1670, 1680,  ```
    ```  1690, 1700, 1710, 1720, 1730, 1740, 1750, 1760, 1770, 1780, 1790, 1800)  ```
    ```  and idx2 in (100, 102, 104, 106, 108, 110, 112, 114, 116, 118, 120, 122,  ```
    ```  124, 126, 128, 130, 132, 134, 136, 138, 140, 142, 144, 146, 148, 150,  ```
    ```  152, 154, 156, 158, 160, 162, 164, 166, 168, 170, 172, 174, 176, 178,  ```
    ```  180, 182, 184, 186, 188, 190, 192, 194, 196, 198, 200, 202, 204, 206,  ```
    ```  208, 210, 212, 214, 216, 218, 220, 222, 224, 226, 228, 230, 232, 234,  ```
    ```  236, 238, 240, 242, 244, 246, 248, 250, 252, 254, 256, 258, 260);  ```
    ```    ```
    ```  NOTE: DATA statement used (Total process time):  ```
    ```        real time           2.80 seconds  ```
    ```        cpu time            2.79 seconds  ```
    ```    ```
    ```    ```
    ```  SPDE PARTITIOND  ```
    ```    ```
    ```  NOTE: There were 2624000 observations read from the data set SPDE.DT.  ```
    ```  WHERE idx in (1000, 1010, 1020, 1030, 1040, 1050, 1060, 1070, 1080,  ```
    ```  1090, 1100, 1110, 1120, 1130, 1140, 1150, 1160, 1170, 1180, 1190, 1200,  ```
    ```  1210, 1220, 1230, 1240, 1250, 1260, 1270, 1280, 1290, 1300, 1310, 1320,  ```
    ```  1330, 1340, 1350, 1360, 1370, 1380, 1390, 1400, 1410, 1420, 1430, 1440,  ```
    ```  1450, 1460, 1470, 1480, 1490, 1500, 1510, 1520, 1530, 1540, 1550, 1560,  ```
    ```  1570, 1580, 1590, 1600, 1610, 1620, 1630, 1640, 1650, 1660, 1670, 1680,  ```
    ```  1690, 1700, 1710, 1720, 1730, 1740, 1750, 1760, 1770, 1780, 1790, 1800)  ```
    ```  and idx2 in (100, 102, 104, 106, 108, 110, 112, 114, 116, 118, 120, 122,  ```
    ```  124, 126, 128, 130, 132, 134, 136, 138, 140, 142, 144, 146, 148, 150,  ```
    ```  152, 154, 156, 158, 160, 162, 164, 166, 168, 170, 172, 174, 176, 178,  ```
    ```  180, 182, 184, 186, 188, 190, 192, 194, 196, 198, 200, 202, 204, 206,  ```
    ```  208, 210, 212, 214, 216, 218, 220, 222, 224, 226, 228, 230, 232, 234,  ```
    ```  236, 238, 240, 242, 244, 246, 248, 250, 252, 254, 256, 258, 260);  ```
    ```    ```
    ```    ```
    ```  NOTE: The data set OUT.L1000 has 2624000 observations and 7 variables.  ```
    ```  NOTE: DATA statement used (Total process time):  ```
    ```        real time           0.99 seconds  ```
    ```        cpu time            1.70 seconds  ```
    ```    ```
    ```  BATCH SETUP  ```
    ```    ```
    ```  * save macro in autocall library;  ```
    ```    ```
    ```  data _null_;file "c:\oto\utl_idx2.sas"  ```
    ```  lrecl=512;input;put _infile_;putlog _infile_;  ```
    ```  cards4;  ```
    ```  %macro utl_idx2(lst=1000,d=c,typ=spde);  ```
    ```    ```
    ```  libname out "&d.:/wrk";  ```
    ```  %utlnopts;  ```
    ```  options source notes;  ```
    ```  data _null_;  ```
    ```    length str $1000;  ```
    ```    str="&lst";  ```
    ```    do i=&lst to %eval(&lst+800) by 10;  ```
    ```      str=cats(str,',',put(i,4.));  ```
    ```    end;  ```
    ```    call symputx('lst1',str);  ```
    ```    str='100';  ```
    ```    do i=%eval(&lst/10) to %eval(&lst/10 +160) by 2;  ```
    ```      str=cats(str,',',put(i,4.));  ```
    ```    end;  ```
    ```    call symputx('lst2',str);  ```
    ```  run;quit;  ```
    ```    ```
    ```  libname out "&d.:/wrk";  ```
    ```    ```
    ```  %if &typ=spde %then %do;  ```
    ```    libname spde spde  ```
    ```     ('c:\wrk\spde_c','d:\wrk\spde_d','e:\wrk\spde_e','g:\wrk\spde_g','h:\wrk\spde_h')  ```
    ```        metapath =('c:\wrk\spde_c\metadata')  ```
    ```        indexpath=(  ```
    ```              'c:\wrk\spde_c'  ```
    ```              ,'d:\wrk\spde_d'  ```
    ```              ,'e:\wrk\spde_e'  ```
    ```              ,'g:\wrk\spde_g'  ```
    ```              ,'h:\wrk\spde_h')  ```
    ```    ```
    ```        datapath =(  ```
    ```            /*  'c:\wrk\spde_c'  ```
    ```              ,'d:\wrk\spde_d'  ```
    ```              ,*/ 'e:\wrk\spde_e'  ```
    ```              ,'g:\wrk\spde_g'  ```
    ```              ,'h:\wrk\spde_h')  ```
    ```     ;  ```
    ```    ```
    ```     /*  ```
    ```         %let lst=7000;  ```
    ```         %let d=c;  ```
    ```     */  ```
    ```    ```
    ```    data out.l&lst;  ```
    ```      set spde.dt(where=(idx in (&lst1) and  ```
    ```                    idx2 in (&lst2) ));  ```
    ```     run;quit;  ```
    ```  %end;  ```
    ```  %else %do;  ```
    ```  libname inp "e:\wrk";  ```
    ```  data out.l&lst;;  ```
    ```    set inp.wrk_dt(where=(idx in (&lst1) and  ```
    ```                      idx2 in (&lst2) ));  ```
    ```  run;quit;  ```
    ```    ```
    ```  %end;  ```
    ```    ```
    ```  %mend utl_idx2;  ```
    ```  ;;;;  ```
    ```  ;run;quit;  ```
    ```    ```
    ```  * test it out interactively;  ```
    ```  * you need to highlight macro in datastep above and hit RMB;  ```
    ```    ```
    ```  %utl_idx2(lst=1000,d=c);  ```
    ```  %utl_idx2(lst=2000,d=c);  ```
    ```  %utl_idx2(lst=1000,d=c,typ=work);  ```
    ```    ```
    ```  * RUN BATCH  ```
    ```  %let tym=%sysfunc(time());  ```
    ```  systask kill sys101;  ```
    ```  systask command "&_s -termstmt %nrstr(%utl_idx2(lst=1000,d=c);) -log G:\wrk\sysspd1.log" taskname=sys101;  ```
    ```  systask list;  ```
    ```  %put %sysevalf( %sysfunc(time()) - &tym);  ```
    ```    ```
    ```  %let tym=%sysfunc(time());  ```
    ```  systask kill sys102;  ```
    ```  systask command "&_s -termstmt %nrstr(%utl_idx2(lst=1000,typ=work,d=c);) -log G:\wrk\sysspd2.log" taskname=sys102;  ```
    ```  systask list;  ```
    ```  %put %sysevalf( %sysfunc(time()) - &tym);  ```
    ```    ```
    ```    ```
    ```    ```
