---
title: Ejemplos de la instrucción SELECT en mySAP adaptador en BizTalk | Documentos de Microsoft
description: Seleccione ejemplos y ejemplos de uso del adaptador de mySAP en el módulo de adaptador de BizTalk (BAP)
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 54a5a4ac-a994-4706-9735-a5a1a82b893b
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 140e895bf8ec2fb65a848c8752dc8e141530bd85
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22216132"
---
# <a name="examples-for-select-statement"></a>Ejemplos de la instrucción SELECT
Este tema muestra la sintaxis de ejemplo para varias instrucciones SELECT.

## <a name="sample-statements"></a>Instrucciones de ejemplo 
  
-   Para mostrar detalles sobre los vuelos enumerados en la tabla denominada SPFLI, use la siguiente sintaxis:  
  
    ```  
    Select * from SPFLI  
    ```  
  
-   Para almacenar los datos extraídos en un archivo denominado flight.txt en \\\SAPServer\Extracts, use la siguiente sintaxis:  
  
    ```  
    Select * Into file '\\SAPServer\Extracts\flight.txt' from SPFLI  
    ```  
  
-   Para mostrar los detalles de todos los vuelos de Nueva York a San Francisco, use la sintaxis siguiente:  
  
    ```  
    Select * from SPFLI where cityfrom='NEW YORK' and cityto='SAN FRANCISCO'  
    ```  
  
-   Para mostrar los detalles de todos los vuelos de Nueva York cuyo `connid` valores de campo están comprendidos entre 1000 y 5000, use la sintaxis siguiente:  
  
    ```  
    Select * from SPFLI where cityfrom='NEW YORK' and (connid>1000 and connid<5000)  
    ```  
  
-   Para mostrar los detalles de todos los vuelos de Nueva York a una ciudad especificada por el usuario, use la sintaxis siguiente:  
  
    ```  
    Select * from SPFLI where cityfrom='NEW YORK' and cityto=@variable  
    ```  
  
     En este caso, cree un parámetro SAP denominado `@variable`, especifique el valor y agregarlo al objeto de comando correspondiente.  
  
-   En la cláusula LIKE de una consulta SELECT, el signo de porcentaje, "%" (para cualquier cadena de cero o más caracteres) y carácter de subrayado "_" (para cualquier carácter individual) son caracteres especiales permitidos. Todos los demás se consideran valores de cadena y se omiten.  
  
    -   Ejemplo para mostrar el uso de porcentaje "%"  
  
        ```  
        SELECT NAME1, PSTLZ  from KNA1 where (MANDT between 596 AND 999) AND NAME1 LIKE '%MODE%'  
        ```  
  
         En este caso, el modo % captura todos los registros donde nombre1 contiene la cadena "Modo de".  
  
    -   Ejemplo para mostrar el uso del carácter de subrayado "_"  
  
        ```  
        SELECT NAME1  AS [MYANME],  LAND1, KUNNR  from KNA1 where (NAME1 LIKE 'D_' )  
        ```  
  
         En este caso, "D_" captura todos los registros donde nombre1 comienza con "D" y contiene dos caracteres.  
  
-   Ejemplo para demostrar una cláusula de predicado "between"  
  
    ```  
    SELECT NAME1, PSTLZ  from KNA1 where (MANDT between 596 AND 999) AND NAME1 LIKE '%MODE%'  
    ```  
  
-   Ejemplo para demostrar una cláusula de predicado "no entre"  
  
    ```  
    SELECT NAME1, PSTLZ  from KNA1 where (MANDT not between 596 AND 599) AND NAME1 LIKE '%MODE%'  
    ```  
  
-   Ejemplo de la instrucción SELECT con una cláusula TOP y combinación  
  
    ```  
    SELECT TOP 1 * FROM spfli INNER JOIN sflight ON spfli.mandt = sflight.mandt  
    ```  
  
-   Ejemplo de la instrucción SELECT que utiliza la cláusula OPTION  
  
    ```  
    SELECT top 50000 * from bseg option 'batchsize 20000'  
    ```  
