---
title: Ejemplos de instrucción EXECQUERY de mySAP adaptador en BizTalk | Documentos de Microsoft
description: Ejemplos EXECQUERY y ejemplos de uso del adaptador de mySAP en el módulo de adaptador de BizTalk (BAP)
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4139af16-7c38-4ea2-b3e5-5acf8fc1f3c4
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 77c5d5877ff502b8fdca620d8b92e4427d3b73b8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22216244"
---
# <a name="examples-for-execquery-statement"></a>Ejemplos de instrucción EXECQUERY
Este tema proporciona instrucciones de EXECQUERY de ejemplo.  


## <a name="sample-statements"></a>Instrucciones de ejemplo
-   Comando para ejecutar una consulta que toma dos parámetros P1 y P2.  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 = '0000003262',@P2 = 'La Quinta Hotel & Towers'  
    ```  
  
-   Comando que se va a ejecutar una consulta que acepta un rango del valor de parámetro P1.  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 BETWEEN '0000003262' AND '0000003265'  
    ```  
  
-   Comando que se va a ejecutar una consulta que tiene los valores de parámetro P1 fuera de un intervalo determinado.  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', NOT @P1 BETWEEN '0000003262' AND '0000003265'  
    ```  
  
-   Comando que se va a ejecutar una consulta que puede tomar uno de dos valores de parámetro P1.  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 = '0000003262', @P1 = '0000003263'  
    ```  
  
-   Comando para ejecutar una consulta que no puede tener valores específicos para los parámetros.  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', NOT @P1 = '0000003262', NOT @P2 = '0000003263'  
    ```  
  
     En este ejemplo, P1 puede tener cualquier valor distinto de '0000003262'. De forma similar, P2 puede tener cualquier valor distinto de '0000003263'.  
  
-   Comando que se va a ejecutar una consulta que tiene variantes definidas en el sistema SAP.  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @variant = ‘variant1’  
    ```  
  
     Variantes hacen referencia a un conjunto de criterios de selección que puede especificar al ejecutar una consulta SAP almacenado. Por ejemplo, puede usar variantes para especificar valores predeterminados para las consultas. Para las consultas que tienen variantes definidas para todos los parámetros, no es necesario especificar los parámetros en el texto del comando.  
  
-   Comando que se va a ejecutar una consulta que no requiere un parámetro.  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 = 'some_dummy_value'  
    ```  
  
     Para las consultas que no tienen parámetros, debe especificar un parámetro con un valor ficticio.  
  
-   Comando para ejecutar una consulta que contenga un parámetro que se esperaba un valor de fecha.  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 = '20080606'  
    ```  
  
     Para las consultas que toman parámetros espera valores de fecha, debe especificar la fecha AAAAMMDD.  
  
-   Comando para ejecutar una consulta mediante la especificación de valores null para los parámetros.  
  
     Para estas consultas, no se puede especificar una consulta como:  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 = 'null'  
    ```  
  
     En su lugar, si no desea especificar un valor, no debe especificar P1 en absoluto.  
  
-   Comando para ejecutar una consulta que contenga un parámetro que se esperaba un valor mayor que un número determinado.  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 > '0000003262'  
    ```  
  
-   Comando para ejecutar una consulta que contenga un parámetro que se espera un valor menor que un número determinado.  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 < '0000003262'  
    ```  
  
-   Comando para ejecutar una consulta que contenga un parámetro que se esperaba un valor mayor o igual a un número determinado.  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 >= '0000003262'  
    ```  
  
-   Comando para ejecutar una consulta que contenga un parámetro que se esperaba un valor menor o igual que un número determinado.  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 <= '0000003262'  
    ```  
  
-   Comando para ejecutar una consulta que contenga un parámetro que se espera un valor no es igual a un número determinado.  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 != '0000003262'  
    ```  
  