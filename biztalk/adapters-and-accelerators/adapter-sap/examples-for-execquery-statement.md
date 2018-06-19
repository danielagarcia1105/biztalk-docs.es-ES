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
# <a name="examples-for-execquery-statement"></a><span data-ttu-id="fe612-103">Ejemplos de instrucción EXECQUERY</span><span class="sxs-lookup"><span data-stu-id="fe612-103">Examples for EXECQUERY Statement</span></span>
<span data-ttu-id="fe612-104">Este tema proporciona instrucciones de EXECQUERY de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="fe612-104">This topic provides sample EXECQUERY statements.</span></span>  


## <a name="sample-statements"></a><span data-ttu-id="fe612-105">Instrucciones de ejemplo</span><span class="sxs-lookup"><span data-stu-id="fe612-105">Sample statements</span></span>
-   <span data-ttu-id="fe612-106">Comando para ejecutar una consulta que toma dos parámetros P1 y P2.</span><span class="sxs-lookup"><span data-stu-id="fe612-106">Command to execute a query that takes two parameters P1 and P2.</span></span>  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 = '0000003262',@P2 = 'La Quinta Hotel & Towers'  
    ```  
  
-   <span data-ttu-id="fe612-107">Comando que se va a ejecutar una consulta que acepta un rango del valor de parámetro P1.</span><span class="sxs-lookup"><span data-stu-id="fe612-107">Command to execute a query that takes a range of value for parameter P1.</span></span>  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 BETWEEN '0000003262' AND '0000003265'  
    ```  
  
-   <span data-ttu-id="fe612-108">Comando que se va a ejecutar una consulta que tiene los valores de parámetro P1 fuera de un intervalo determinado.</span><span class="sxs-lookup"><span data-stu-id="fe612-108">Command to execute a query that takes values for parameter P1 outside a particular range.</span></span>  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', NOT @P1 BETWEEN '0000003262' AND '0000003265'  
    ```  
  
-   <span data-ttu-id="fe612-109">Comando que se va a ejecutar una consulta que puede tomar uno de dos valores de parámetro P1.</span><span class="sxs-lookup"><span data-stu-id="fe612-109">Command to execute a query that can take one of two values for parameter P1.</span></span>  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 = '0000003262', @P1 = '0000003263'  
    ```  
  
-   <span data-ttu-id="fe612-110">Comando para ejecutar una consulta que no puede tener valores específicos para los parámetros.</span><span class="sxs-lookup"><span data-stu-id="fe612-110">Command to execute a query that cannot take specific values for parameters.</span></span>  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', NOT @P1 = '0000003262', NOT @P2 = '0000003263'  
    ```  
  
     <span data-ttu-id="fe612-111">En este ejemplo, P1 puede tener cualquier valor distinto de '0000003262'.</span><span class="sxs-lookup"><span data-stu-id="fe612-111">In this example, P1 can have any value other than '0000003262'.</span></span> <span data-ttu-id="fe612-112">De forma similar, P2 puede tener cualquier valor distinto de '0000003263'.</span><span class="sxs-lookup"><span data-stu-id="fe612-112">Similarly, P2 can have any value other than '0000003263'.</span></span>  
  
-   <span data-ttu-id="fe612-113">Comando que se va a ejecutar una consulta que tiene variantes definidas en el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="fe612-113">Command to execute a query that has variants defined in the SAP system.</span></span>  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @variant = ‘variant1’  
    ```  
  
     <span data-ttu-id="fe612-114">Variantes hacen referencia a un conjunto de criterios de selección que puede especificar al ejecutar una consulta SAP almacenado.</span><span class="sxs-lookup"><span data-stu-id="fe612-114">Variants refer to a saved set of selection criteria that you can specify while executing an SAP query.</span></span> <span data-ttu-id="fe612-115">Por ejemplo, puede usar variantes para especificar valores predeterminados para las consultas.</span><span class="sxs-lookup"><span data-stu-id="fe612-115">For example, you can use variants to specify default values for queries.</span></span> <span data-ttu-id="fe612-116">Para las consultas que tienen variantes definidas para todos los parámetros, no es necesario especificar los parámetros en el texto del comando.</span><span class="sxs-lookup"><span data-stu-id="fe612-116">For queries that have variants defined for all parameters, you do not need to specify the parameters in the command text.</span></span>  
  
-   <span data-ttu-id="fe612-117">Comando que se va a ejecutar una consulta que no requiere un parámetro.</span><span class="sxs-lookup"><span data-stu-id="fe612-117">Command to execute a query that does not require a parameter.</span></span>  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 = 'some_dummy_value'  
    ```  
  
     <span data-ttu-id="fe612-118">Para las consultas que no tienen parámetros, debe especificar un parámetro con un valor ficticio.</span><span class="sxs-lookup"><span data-stu-id="fe612-118">For queries that do not take parameter, you must specify a parameter with a dummy value.</span></span>  
  
-   <span data-ttu-id="fe612-119">Comando para ejecutar una consulta que contenga un parámetro que se esperaba un valor de fecha.</span><span class="sxs-lookup"><span data-stu-id="fe612-119">Command to execute a query containing a parameter expecting a date value.</span></span>  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 = '20080606'  
    ```  
  
     <span data-ttu-id="fe612-120">Para las consultas que toman parámetros espera valores de fecha, debe especificar la fecha AAAAMMDD.</span><span class="sxs-lookup"><span data-stu-id="fe612-120">For queries that take parameters expecting date values, you must specify the date as YYYYMMDD.</span></span>  
  
-   <span data-ttu-id="fe612-121">Comando para ejecutar una consulta mediante la especificación de valores null para los parámetros.</span><span class="sxs-lookup"><span data-stu-id="fe612-121">Command to execute a query by specifying null values for parameters.</span></span>  
  
     <span data-ttu-id="fe612-122">Para estas consultas, no se puede especificar una consulta como:</span><span class="sxs-lookup"><span data-stu-id="fe612-122">For such queries, you cannot specify a query as:</span></span>  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 = 'null'  
    ```  
  
     <span data-ttu-id="fe612-123">En su lugar, si no desea especificar un valor, no debe especificar P1 en absoluto.</span><span class="sxs-lookup"><span data-stu-id="fe612-123">Instead, if you do not want to specify a value, you should not specify P1 at all.</span></span>  
  
-   <span data-ttu-id="fe612-124">Comando para ejecutar una consulta que contenga un parámetro que se esperaba un valor mayor que un número determinado.</span><span class="sxs-lookup"><span data-stu-id="fe612-124">Command to execute a query containing a parameter expecting a value greater than a certain number.</span></span>  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 > '0000003262'  
    ```  
  
-   <span data-ttu-id="fe612-125">Comando para ejecutar una consulta que contenga un parámetro que se espera un valor menor que un número determinado.</span><span class="sxs-lookup"><span data-stu-id="fe612-125">Command to execute a query containing a parameter expecting a value lesser than a certain number.</span></span>  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 < '0000003262'  
    ```  
  
-   <span data-ttu-id="fe612-126">Comando para ejecutar una consulta que contenga un parámetro que se esperaba un valor mayor o igual a un número determinado.</span><span class="sxs-lookup"><span data-stu-id="fe612-126">Command to execute a query containing a parameter expecting a value greater or equal to a certain number.</span></span>  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 >= '0000003262'  
    ```  
  
-   <span data-ttu-id="fe612-127">Comando para ejecutar una consulta que contenga un parámetro que se esperaba un valor menor o igual que un número determinado.</span><span class="sxs-lookup"><span data-stu-id="fe612-127">Command to execute a query containing a parameter expecting a value lesser or equal to a certain number.</span></span>  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 <= '0000003262'  
    ```  
  
-   <span data-ttu-id="fe612-128">Comando para ejecutar una consulta que contenga un parámetro que se espera un valor no es igual a un número determinado.</span><span class="sxs-lookup"><span data-stu-id="fe612-128">Command to execute a query containing a parameter expecting a value not equal to a certain number.</span></span>  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 != '0000003262'  
    ```  
  