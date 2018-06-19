---
title: Determinar si una columna almacena valores en mayúsculas o minúsculas | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1edc8332-d8c7-4040-895b-f121fb03df44
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 93b54c00b43192462fb095dbfbfda4cbf0b248a0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22216988"
---
# <a name="determining-whether-a-column-stores-lowercase-or-uppercase-values"></a><span data-ttu-id="c242c-102">Determinar si un columna almacena los valores en mayúsculas o minúsculas</span><span class="sxs-lookup"><span data-stu-id="c242c-102">Determining Whether a Column Stores Lowercase or Uppercase Values</span></span>
<span data-ttu-id="c242c-103">Esta sección enumeran las tareas de alto nivel que se realizarán en el sistema SAP para determinar si una columna de una tabla SAP almacena caracteres en mayúsculas o minúsculas.</span><span class="sxs-lookup"><span data-stu-id="c242c-103">This section lists high-level tasks to be performed on the SAP system to determine whether a column in an SAP table stores lowercase or uppercase characters.</span></span> <span data-ttu-id="c242c-104">Para obtener instrucciones detalladas sobre cómo realizar esta tarea debe ponerse en contacto con el Administrador de SAP o consulte la documentación de SAP.</span><span class="sxs-lookup"><span data-stu-id="c242c-104">For detailed instructions on how to perform this task you must contact your SAP administrator or refer to SAP documentation.</span></span>  
  
### <a name="to-determine-the-case-of-values-stored-in-a-column"></a><span data-ttu-id="c242c-105">Para determinar el caso de los valores almacenados en una columna</span><span class="sxs-lookup"><span data-stu-id="c242c-105">To determine the case of values stored in a column</span></span>  
  
1.  <span data-ttu-id="c242c-106">Inicie la GUI de SAP.</span><span class="sxs-lookup"><span data-stu-id="c242c-106">Start the SAP GUI.</span></span>  
  
2.  <span data-ttu-id="c242c-107">Vaya a la transacción SE37 y ejecute DDIF_TABL_GET.</span><span class="sxs-lookup"><span data-stu-id="c242c-107">Go to Transaction SE37 and execute DDIF_TABL_GET.</span></span>  
  
3.  <span data-ttu-id="c242c-108">Para el parámetro de nombre, especifique el nombre de tabla que contiene la columna para la que desea determinar la información del caso de carácter.</span><span class="sxs-lookup"><span data-stu-id="c242c-108">For the NAME parameter, specify the table name containing the column for which you want to determine the character case information.</span></span> <span data-ttu-id="c242c-109">Por ejemplo, KNA1.</span><span class="sxs-lookup"><span data-stu-id="c242c-109">For example, KNA1.</span></span>  
  
4.  <span data-ttu-id="c242c-110">El primer parámetro de tabla es DD03P_TAB.</span><span class="sxs-lookup"><span data-stu-id="c242c-110">The first table parameter is DD03P_TAB.</span></span> <span data-ttu-id="c242c-111">Haga clic en el parámetro para ver las filas de la tabla.</span><span class="sxs-lookup"><span data-stu-id="c242c-111">Click the parameter to see the rows in the table.</span></span> <span data-ttu-id="c242c-112">Cada fila de esta tabla corresponde a una columna en la tabla (por ejemplo, KNA1) especificó en el paso 3.</span><span class="sxs-lookup"><span data-stu-id="c242c-112">Every row in this table corresponds to a column in the table (such as KNA1) you specified in step 3.</span></span>  
  
5.  <span data-ttu-id="c242c-113">En DD03P_TAB, busque el valor de la columna para cada fila en MINÚSCULAS.</span><span class="sxs-lookup"><span data-stu-id="c242c-113">In DD03P_TAB, look for the value in the LOWERCASE column for each row.</span></span> <span data-ttu-id="c242c-114">Si el valor de la columna en MINÚSCULAS es 'X', la columna correspondiente en la tabla (por ejemplo, KNA1), puede almacenar los caracteres en mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="c242c-114">If the value in the LOWERCASE column is 'X', the corresponding column in the table (such as KNA1), can store both lowercase and uppercase characters.</span></span> <span data-ttu-id="c242c-115">Si el valor de la columna en MINÚSCULAS está vacío, la columna correspondiente sólo puede almacenar caracteres en mayúsculas.</span><span class="sxs-lookup"><span data-stu-id="c242c-115">If the value in the LOWERCASE column is empty, the corresponding column can only store uppercase characters.</span></span>  
  
     <span data-ttu-id="c242c-116">Por ejemplo, para la fila de nombre minúscula columna es X. Por lo tanto, la columna NAME de KNA1 puede almacenar caracteres en mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="c242c-116">For example, for the NAME row the LOWERCASE column is X. So, the NAME column in KNA1 can store both uppercase and lowercase characters.</span></span> <span data-ttu-id="c242c-117">Sin embargo, para la fila de LAND1 minúscula columna está vacía.</span><span class="sxs-lookup"><span data-stu-id="c242c-117">However, for the LAND1 row the LOWERCASE column is empty.</span></span> <span data-ttu-id="c242c-118">Por lo tanto, la columna LAND1 en KNA1 tabla solo puede almacenar caracteres en mayúsculas.</span><span class="sxs-lookup"><span data-stu-id="c242c-118">So, the LAND1 column in KNA1 table can only store uppercase characters.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c242c-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="c242c-119">See Also</span></span>  
 [<span data-ttu-id="c242c-120">Realizar tareas mediante la GUI de SAP para escenarios de adaptadores SAP específicos</span><span class="sxs-lookup"><span data-stu-id="c242c-120">Performing Tasks Using the SAP GUI for Specific SAP Adapter Scenarios</span></span>](../../adapters-and-accelerators/adapter-sap/performing-tasks-using-the-sap-gui-for-specific-sap-adapter-scenarios.md)