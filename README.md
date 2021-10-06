;Uilização de emulator PuTTy com edito G.TM
;Código compilado para PSL/Mumps
;Novo Ecran para Cedência de Sindicato

^DBTBL("SYSDEV",2,"********",0,1)= ;
                           1.001)= ;hipoteses de cedência de sindicato
                           1.002)= ;                                    Todas caixas para OIC
                           1.003)= I (%O=0)!(%O=1) D
                           1.004)= . I [ZFDLN917]PTIPO\1=2 D
                           1.005)= ..  .UNPROT. [ZFDLN917]OIC
                           1.006)= ..  .UNPROT. [ZFDLN917]MPARC
                           1.007)= ..  .UNPROT. [ZFDLN917]PERCENT
                           1.008)= ..  .PROTECT. [ZFDLN917]CCAMORI
                           1.009)= ..  .PROTECT. [ZFDLN917]CCAMDST
                            1.01)= .;                                   Uma caixa para OIC
                           1.011)= . I [ZFDLN917]PTIPO\1=3 D
                           1.012)= ..  .UNPROT. [ZFDLN917]CCAMORI
                           1.013)= ..  .UNPROT. [ZFDLN917]OIC
                           1.014)= ..  .UNPROT. [ZFDLN917]MPARC
                           1.015)= ..  .UNPROT. [ZFDLN917]PERCENT
                           1.016)= ..  .PROTECT. [ZFDLN917]CCAMDST
                           1.017)= .;                                   Caixa para caixa
                           1.018)= . I [ZFDLN917]PTIPO\1=4 D
                           1.019)= ..  .UNPROT. [ZFDLN917]CCAMORI
                            1.02)= ..  .UNPROT. [ZFDLN917]CCAMDST
                           1.021)= ..  .UNPROT. [ZFDLN917]MPARC
                           1.022)= ..  .UNPROT. [ZFDLN917]PERCENT
                           1.023)= ..  .PROTECT. [ZFDLN917]OIC
                           1.024)= .;
                           1.025)= ;
                           1.026)= I (%O=2)!(%O=3) D                            ;Para opção de consultar e eliminar
                           1.027)= . .PROTECT. [ZFDLN917]OIC
                           1.028)= . .PROTECT. [ZFDLN917]MPARC
                           1.029)= . .PROTECT. [ZFDLN917]PERCENT
                            1.03)= . .PROTECT. [ZFDLN917]CCAMORI
                           1.031)= . .PROTECT. [ZFDLN917]CCAMDST
                           1.032)= ;
                           1.033)= .DEFAULT./UX [ZFDLN917]ZPERSON=$P($G(^ZFDLN903(CODSIND)),"|",3)
                           1.034)= ;
                              81)=12Mai2020-EA-Eduardo Alves
                              82)=       Novo Ecran para Cedência de Sindicato
                             121)= S PTIPODES=$P($G(^UTBL("ZTDLN291",[ZFDLN917]PTIPO\1)),"|",1)
                         121.001)= ;
                         121.002)= I %O D
                         121.003)= . I PTIPO\1=2 D
                         121.004)= .. S OICDESC=$$DESCOIC([ZFDLN917]OIC)
                         121.005)= .. S DESCPAP=$$DESCPAP([ZFDLN917]PAPEL)
                         121.006)= .. Q
                         121.007)= . ;
                         121.008)= . I PTIPO\1=3 D
                         121.009)= .. S ORIGDESC=$$DESCBRCD([ZFDLN917]CCAMORI)
                          121.01)= .. S OICDESC=$$DESCOIC([ZFDLN917]OIC)
                         121.011)= .. S DESCPAP=$$DESCPAP([ZFDLN917]PAPEL)
                         121.012)= .. Q
                         121.013)= .;
                         121.014)= . I PTIPO\1=4 D
                         121.015)= .. S ORIGDESC=$$DESCBRCD([ZFDLN917]CCAMORI)
                         121.016)= .. S DESTDESC=$$DESCBRCD([ZFDLN917]CCAMDST)
                         121.017)= .. S DESCPAP=$$DESCPAP([ZFDLN917]PAPEL)
                         121.018)= ;
                         121.019)= Q
                          121.02)= ;
                         121.021)=DESCOIC(X)
                         121.022)= ;
                         121.023)= Q:X="" ""
                         121.024)= ;
                         121.025)= Q $P($G(^UTBL("ZTDYY108",X)),"|",1)
                         121.026)= ;
                         121.027)=DESCBRCD(X)
                         121.028)= ;
                         121.029)= Q:X="" ""
                          121.03)= ;
                         121.031)= Q $P($G(^UTBL("BRCD",X)),"|",1)
                         121.032)= ;
                         121.033)= Q DESCBRCD
                         121.034)= ;
                         121.035)=DESCPAP(X)
                         121.036)= ;
                         121.037)= Q:X="" ""
                         121.038)= ;
                         121.039)= Q $G(^UTBL("ZTDLN238",X))
                          121.04)= ;
^DBTBL("SYSDEV",2,"ZSDLM286",1)=1001*#66,0,0,0,0,0,0|*|||@ooe1|||||T|SINDICATOS
                             2)=1023*#66,0,0,0,0,0,0|*|10||@ooe2|||||T|<<$$TIT^ZPDZZ100(0)>>|
                             3)=1034*#66,0,0,0,0,0,0|*|||@ooe3|||||T|CEDÊNCIA DE SINDICATO
                             4)=1063*#66,0,0,0,0,0,0|*|10||@ooe1|||||T|<<$$DAT^%ZM>>|
                             5)=1074*#66,0,0,0,0,0,0|*|5||@ooe2|||||D|<<$$TIM^%ZM>>|||||||T|
                             6)=4005*#64,0,0,0,0,0,0|*|||@ooe6|||||T|Data Cedência    :
                             7)=4024*#66,0,0,0,0,0,0|@ooe6|10||[SYSDEV,ZFDLN917]TJD|||||D||1|||||||||124|
                             8)=6005*#64,0,0,0,0,0,0|*|||@ooe8|||||T|Sindicato        :
                             9)=6024*#66,0,0,0,0,0,0|@ooe8|9||[SYSDEV,ZFDLN903]CODSIND|||||N||1|||||||||124|
                            10)=6042*#64,0,0,0,0,0,0|*|||@ooe10|||||T| Conta Personalizada:
                            11)=6064*#66,0,0,0,0,0,0|@ooe10|12||[SYSDEV,ZFDLN903]ZPERSON|||||N||1|||||||||124|3
                            12)=8005*#64,0,0,0,0,0,0|*|||@ooe12|||||T|Cliente          :
                            13)=8024*#66,0,0,0,0,0,0|@ooe12|12||[SYSDEV,ZFDLN903]ACN|[CIF]||||N||1|||||||||124|1
                            14)=10005*#64,0,0,0,0,0,0|*|||@ooe14|||||T|Nome Cliente     :
                            15)=10024*#66,0,0,0,0,0,0|@ooe14|52||[SYSDEV,ZFDLN903]NAM|||||T||1|
                            16)=12005*#64,0,0,0,0,0,0|*|||@ooe16|||||T|Tipo Cedência    :
                            17)=12024*#66,0,0,0,0,0,0|@ooe16|5||[SYSDEV,ZFDLN917]PTIPO|[ZFDLM158]||||N||1|||3||||||124|
                            18)=12032*#66,0,0,0,0,0,0|*|40||@PTIPODES|||||T|<<PTIPODES>>|
                            19)=14005*#65,0,0,0,0,0,0|*|||@ooe19|||||T|CCAM Origem      :
                            20)=14024#66,0,0,0,0,0,0|@ooe19|4||[SYSDEV,ZFDLN917]CCAMORI|[UTBLBRCD]||1|1|N||1|||||||||124|5
^DBTBL("SYSDEV",2,"ZSDLM286",20,1)= ; .CHANGE. TBL="[ZFDLN904]ENTFIA,ENTFIADES:QU ""TIPOENT='01' AND ENTFIA'=9990 AND CODSIND=<<CODSIND>>"""
                                2)= .CHANGE. TBL="[ZFDLN904]ENTFIA,ENTFIADES:QU ""TIPOENT='01' AND CODSIND=<<CODSIND>>"""
                                3)= ;
                               21)= .DEFAULT. @ORIGDESC=""
                               22)= Q:X=""
                               23)= .DEFAULT. @ORIGDESC=$$DESCBRCD(X)
                               24)= ;
                               25)= N BAL,CID
                               26)= ;
                               27)= S CID=$$CCAMCID^ZPDLN496(CODSIND,X)
                               28)= ;
                               29)= I CID="" S ER=1,RM="CCAM não tem conta definida" Q
                               30)= ;
                               31)= S BAL=+$P($G(^ACN(CID,51)),"|",1)
                               32)= ;
                               33)= I BAL=0 S ER=1,RM="Conta sem saldo" Q
                               34)= ;
                               35)= I '$P($G(^ACN(CID,2000)),"|",1) S RM="Conta sem Pagamento Automático."
                               36)= ;
                               37)= S ZAREQ=BAL
^DBTBL("SYSDEV",2,"ZSDLM286",21)=14032*#66,0,0,0,0,0,0|*|40||@ORIGDESC|||||T|<<ORIGDESC>>|
                             22)=15005*#65,0,0,0,0,0,0|*|||@ooe22|||||T|Balcão Destino   :
                             23)=15024#66,0,0,0,0,0,0|@ooe22|4||[SYSDEV,ZFDLN917]CCAMDST|[UTBLBRCD]||1||N||1|||||||||124|6
^DBTBL("SYSDEV",2,"ZSDLM286",23,21)= ;
                            21.001)= .DEFAULT. @DESTDESC=""
                            21.002)= ;
                            21.003)= Q:X=""
                            21.004)= ;
                            21.005)= N CCAM
                            21.006)= ;
                            21.007)= S CCAM=$$CCAM^ZPDZZ100(X,1)
                            21.008)= ;
                            21.009)= I CCAM="" S ER=1,RM="Balcão inválido" Q
                             21.01)= ;
                            21.011)= I [ZFDLN917]CCAMORI=CCAM S ER=1,RM="CCAM Origem igual CCAM destino" Q
                            21.012)= ;
                            21.013)= .DEFAULT. @DESTDESC=$$DESCBRCD(X)
                            21.014)= ;
                            21.015)= .UNPROT. [ZFDLN917]PAPEL
                            21.016)= ;
                            21.017)= I $D(^ZFDLN903(CODSIND,CCAM)) D
                            21.018)= . ;
                            21.019)= . N PAPEL
                             21.02)= . S PAPEL=$P($G(^ZFDLN903(CODSIND,CCAM)),"|",1)
                            21.021)= . ;
                            21.022)= . .DEFAULT. @DESCPAP=$$DESCPAP(PAPEL)
                            21.023)= . .DEFAULT./UX [ZFDLN917]PAPEL=PAPEL
                            21.024)= . .PROTECT. [ZFDLN917]PAPEL
                            21.025)= ;
^DBTBL("SYSDEV",2,"ZSDLM286",24)=15032*#66,0,0,0,0,0,0|*|40||@DESTDESC|||||T|<<DESTDESC>>|1|
                             25)=16005*#65,0,0,0,0,0,0|*|||@ooe25|||||T|OIC Destino      :
                             26)=16024#66,0,0,0,0,0,0|@ooe25|6||[SYSDEV,ZFDLN917]OIC|[ZFDYY134]||1||N||1|||||||||124|7
^DBTBL("SYSDEV",2,"ZSDLM286",26,21)= .DEFAULT. @OICDESC=""
                                22)= Q:X=""
                                23)= .DEFAULT. @OICDESC=$$DESCOIC(X)
                                24)= ;
                                25)= .UNPROT. [ZFDLN917]PAPEL
                                26)= ;
                                27)= I $D(^ZFDLN903(CODSIND,X)) D
                                28)= . ;
                                29)= . N PAPEL
                                30)= . S PAPEL=$P($G(^ZFDLN903(CODSIND,X)),"|",1)
                                31)= . ;
                                32)= . .DEFAULT. @DESCPAP=$$DESCPAP(PAPEL)
                                33)= . .DEFAULT./UX [ZFDLN917]PAPEL=PAPEL
                                34)= . .PROTECT. [ZFDLN917]PAPEL
                                35)= ;
^DBTBL("SYSDEV",2,"ZSDLM286",27)=16032*#66,0,0,0,0,0,0|*|40||@OICDESC|||||T|<<OICDESC>>|
                             28)=17005*#65,0,0,0,0,0,0|*|||@ooe28|||||T|Papel            :
                             29)=17024#66,0,0,0,0,0,0|@ooe28|2||[SYSDEV,ZFDLN917]PAPEL|[ZFDLN905]||1||T||1|||||||||124|10
^DBTBL("SYSDEV",2,"ZSDLM286",29,21)= .DEFAULT. @DESCPAP=""
                                22)= Q:X=""
                                23)= .DEFAULT. @DESCPAP=$$DESCPAP(X)
                                24)= ;
                                25)= I X="01" D
                                26)= . ;
                                27)= . N ENTFIA
                                28)= . ;
                                29)= . S ENTFIA=""
                                30)= . F  S ENTFIA=$O(^ZFDLN903(CODSIND,ENTFIA)) Q:ENTFIA=""  D  Q:$G(ER)
                                31)= .. ;
                                32)= .. I $P(^ZFDLN903(CODSIND,ENTFIA),"|",1)'="01" Q
                                33)= .. ;
                                34)= .. I ([ZFDLN917]OIC'="")&($P(^ZFDLN903(CODSIND,ENTFIA),"|",3)="02")&(ENTFIA=[ZFDLN917]OIC) Q
                                35)= .. I ([ZFDLN917]CCAMDST'="")&($P(^ZFDLN903(CODSIND,ENTFIA),"|",3)="01")&(ENTFIA=$$CCAM^ZPDZZ100([ZFDLN917]CCAMDST,1)) Q
                                36)= .. ;
                                37)= .. S ER=1,RM="Já existe um Líder para este sindicato"
                                38)= ;
^DBTBL("SYSDEV",2,"ZSDLM286",30)=17032*#66,0,0,0,0,0,0|*|15||@DESCPAP|||||T|<<DESCPAP>>|
                             31)=18005*#65,0,0,0,0,0,0|*|||@ooe31|||||T|Montante Parcial :
                             32)=18024#66,0,0,0,0,0,0|@ooe31|16||[SYSDEV,ZFDLN917]MPARC|||1||$||0|||2||||||124|3
^DBTBL("SYSDEV",2,"ZSDLM286",32,21)= .UNPROT. [ZFDLN917]PERCENT
                                22)= ;
                                23)= I ([ZFDLN917]PTIPO\1=2)&(X>ZAREQ) S ER=1,RM="Atenção. Valor inserido excede o montante do Sindicato" Q
                                24)= ;
                                25)= I ([ZFDLN917]PTIPO\1=3)!([ZFDLN917]PTIPO\1=4) I X>ZAREQ S ER=1,RM="Atenção. Valor inserido excede o montante da CCAM" Q
                                26)= ;
                                27)= I X<0 S ER=1,RM="Não pode ser menor que zero" Q
                                28)= ;
                                29)= Q:+X=0
                                30)= ;
                                31)= .DEFAULT. [ZFDLN917]PERCENT=0
                                32)= ;.DEFAULT. [ZFDLN917]PERCENT=$J((X/ZAREQ)*100,"",4)
                                33)= .PROTECT. [ZFDLN917]PERCENT
                                34)= ;
^DBTBL("SYSDEV",2,"ZSDLM286",33)=19005*#65,0,0,0,0,0,0|*|||@ooe33|||||T|Percentagem      :
                             34)=19024#66,0,0,0,0,0,0|@ooe33|8||[SYSDEV,ZFDLN917]PERCENT|||1||N||1|||4||||||124|8
^DBTBL("SYSDEV",2,"ZSDLM286",34,21)= ;
                                22)= I X>100 S ER=1,RM="Não pode exceder 100%" Q
                                23)= I X<0 S ER=1,RM="Não pode ser menor que zero" Q
                                24)= I X=0 S ER=1,RM="Não pode ser zero" Q
                                25)= ;
                                26)= Q:X=""
                                27)= ;
                                28)= .DEFAULT. [ZFDLN917]MPARC=0
                                29)= ;.DEFAULT. [ZFDLN917]MPARC=$J(ZAREQ*X/100,"",2)
                                30)= ;
                                31)= D VALCED^ZPDLN562(CODSIND,PTIPO,[ZFDLN917]CCAMORI,TJD,X)
                                32)= ;
^DBTBL("SYSDEV",2,"ZSDLM286",35)=20005*#65,0,0,0,0,0,0|*|||@ooe35|||||T|Processado       :
                             36)=20024*#66,0,0,0,0,0,0|@ooe35|1||[SYSDEV,ZFDLN917]PROC|||||L||0|||||||||124|2
