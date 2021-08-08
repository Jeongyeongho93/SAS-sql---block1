# SAS-sql---block1
These corn seeds taken by three different are land and watch

DATA corn;
  DO insecide = 1 TO 3;
     DO block = 1 TO 4;
        INPUT insecide @; OUTPUT;
     END;
  END;
DATALINES;
56 49 65 60
84 78 94 93
80 72 83 85
;
RUN;

title;
footnote;
title1 h=10pt f=tahoma j=left 'Corn Seed' j=right 'Protocol No: G-2021-923-JEON';
title2 h=10pt f=tahoma j=left 'OPENSOURCE' j=right 'NON-Confidential';
title4 h=14pt f=tahoma bold j=center 'Corn have not cause fault and spread out on the groud is only fault';
title6 h=10pt f=tahoma j=right 'Date: 20210808 (Signature)';

PROC PRINT DATA = corn;
RUN;

PROC SQL;
SELECT COUNT(block) as Count FROM corn;
WHERE block CONTAINS '1';
QUIT;
RUN;
