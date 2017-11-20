---
title: "Ejemplos de la instrucción SELECT en mySAP adaptador en BizTalk | Documentos de Microsoft"
description: "Seleccione ejemplos y ejemplos de uso del adaptador de mySAP en el módulo de adaptador de BizTalk (BAP)"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 54a5a4ac-a994-4706-9735-a5a1a82b893b
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 140e895bf8ec2fb65a848c8752dc8e141530bd85
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="examples-for-select-statement"></a><span data-ttu-id="8e8e7-103">Ejemplos de la instrucción SELECT</span><span class="sxs-lookup"><span data-stu-id="8e8e7-103">Examples for SELECT Statement</span></span>
<span data-ttu-id="8e8e7-104">Este tema muestra la sintaxis de ejemplo para varias instrucciones SELECT.</span><span class="sxs-lookup"><span data-stu-id="8e8e7-104">This topic shows example syntax for various SELECT statements.</span></span>

## <a name="sample-statements"></a><span data-ttu-id="8e8e7-105">Instrucciones de ejemplo</span><span class="sxs-lookup"><span data-stu-id="8e8e7-105">Sample statements</span></span> 
  
-   <span data-ttu-id="8e8e7-106">Para mostrar detalles sobre los vuelos enumerados en la tabla denominada SPFLI, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="8e8e7-106">To list details about flights listed in the table named SPFLI, use the following syntax:</span></span>  
  
    ```  
    Select * from SPFLI  
    ```  
  
-   <span data-ttu-id="8e8e7-107">Para almacenar los datos extraídos en un archivo denominado flight.txt en \\\SAPServer\Extracts, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="8e8e7-107">To store extracted data into a file named flight.txt at \\\SAPServer\Extracts, use the following syntax:</span></span>  
  
    ```  
    Select * Into file '\\SAPServer\Extracts\flight.txt' from SPFLI  
    ```  
  
-   <span data-ttu-id="8e8e7-108">Para mostrar los detalles de todos los vuelos de Nueva York a San Francisco, use la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="8e8e7-108">To list details of all flights from New York to San Francisco, use the following syntax:</span></span>  
  
    ```  
    Select * from SPFLI where cityfrom='NEW YORK' and cityto='SAN FRANCISCO'  
    ```  
  
-   <span data-ttu-id="8e8e7-109">Para mostrar los detalles de todos los vuelos de Nueva York cuyo `connid` valores de campo están comprendidos entre 1000 y 5000, use la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="8e8e7-109">To list details of all flights from New York whose `connid` field values are between 1000 and 5000, use the following syntax:</span></span>  
  
    ```  
    Select * from SPFLI where cityfrom='NEW YORK' and (connid>1000 and connid<5000)  
    ```  
  
-   <span data-ttu-id="8e8e7-110">Para mostrar los detalles de todos los vuelos de Nueva York a una ciudad especificada por el usuario, use la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="8e8e7-110">To list details of all flights from New York to a user-specified city, use the following syntax:</span></span>  
  
    ```  
    Select * from SPFLI where cityfrom='NEW YORK' and cityto=@variable  
    ```  
  
     <span data-ttu-id="8e8e7-111">En este caso, cree un parámetro SAP denominado `@variable`, especifique el valor y agregarlo al objeto de comando correspondiente.</span><span class="sxs-lookup"><span data-stu-id="8e8e7-111">In this instance, create an SAP parameter named `@variable`, specify the value, and add it to the corresponding command object.</span></span>  
  
-   <span data-ttu-id="8e8e7-112">En la cláusula LIKE de una consulta SELECT, el signo de porcentaje, "%" (para cualquier cadena de cero o más caracteres) y carácter de subrayado "_" (para cualquier carácter individual) son caracteres especiales permitidos.</span><span class="sxs-lookup"><span data-stu-id="8e8e7-112">In the LIKE clause of a SELECT query, only the percent sign, "%" (for any string of zero or more characters), and underscore, "_" (for any single character), are allowable special characters.</span></span> <span data-ttu-id="8e8e7-113">Todos los demás se consideran valores de cadena y se omiten.</span><span class="sxs-lookup"><span data-stu-id="8e8e7-113">All others are considered string values and are ignored.</span></span>  
  
    -   <span data-ttu-id="8e8e7-114">Ejemplo para mostrar el uso de porcentaje "%"</span><span class="sxs-lookup"><span data-stu-id="8e8e7-114">Example to demonstrate the use of percentage "%"</span></span>  
  
        ```  
        SELECT NAME1, PSTLZ  from KNA1 where (MANDT between 596 AND 999) AND NAME1 LIKE '%MODE%'  
        ```  
  
         <span data-ttu-id="8e8e7-115">En este caso, el modo % captura todos los registros donde nombre1 contiene la cadena "Modo de".</span><span class="sxs-lookup"><span data-stu-id="8e8e7-115">Here, %MODE% fetches all records where Name1 contains the string "MODE".</span></span>  
  
    -   <span data-ttu-id="8e8e7-116">Ejemplo para mostrar el uso del carácter de subrayado "_"</span><span class="sxs-lookup"><span data-stu-id="8e8e7-116">Example to demonstrate the use of underscore "_"</span></span>  
  
        ```  
        SELECT NAME1  AS [MYANME],  LAND1, KUNNR  from KNA1 where (NAME1 LIKE 'D_' )  
        ```  
  
         <span data-ttu-id="8e8e7-117">En este caso, "D_" captura todos los registros donde nombre1 comienza con "D" y contiene dos caracteres.</span><span class="sxs-lookup"><span data-stu-id="8e8e7-117">Here, "D_" fetches all records where Name1 starts with "D" and contains two characters.</span></span>  
  
-   <span data-ttu-id="8e8e7-118">Ejemplo para demostrar una cláusula de predicado "between"</span><span class="sxs-lookup"><span data-stu-id="8e8e7-118">Example to demonstrate a "between" predicate clause</span></span>  
  
    ```  
    SELECT NAME1, PSTLZ  from KNA1 where (MANDT between 596 AND 999) AND NAME1 LIKE '%MODE%'  
    ```  
  
-   <span data-ttu-id="8e8e7-119">Ejemplo para demostrar una cláusula de predicado "no entre"</span><span class="sxs-lookup"><span data-stu-id="8e8e7-119">Example to demonstrate a "not between" predicate clause</span></span>  
  
    ```  
    SELECT NAME1, PSTLZ  from KNA1 where (MANDT not between 596 AND 599) AND NAME1 LIKE '%MODE%'  
    ```  
  
-   <span data-ttu-id="8e8e7-120">Ejemplo de la instrucción SELECT con una cláusula TOP y combinación</span><span class="sxs-lookup"><span data-stu-id="8e8e7-120">Example for SELECT statement using Join and a TOP clause</span></span>  
  
    ```  
    SELECT TOP 1 * FROM spfli INNER JOIN sflight ON spfli.mandt = sflight.mandt  
    ```  
  
-   <span data-ttu-id="8e8e7-121">Ejemplo de la instrucción SELECT que utiliza la cláusula OPTION</span><span class="sxs-lookup"><span data-stu-id="8e8e7-121">Example for SELECT statement using the OPTION clause</span></span>  
  
    ```  
    SELECT top 50000 * from bseg option 'batchsize 20000'  
    ```  
