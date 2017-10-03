---
title: "Determinar si una columna almacena valores en mayúsculas o minúsculas | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1edc8332-d8c7-4040-895b-f121fb03df44
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 93b54c00b43192462fb095dbfbfda4cbf0b248a0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="determining-whether-a-column-stores-lowercase-or-uppercase-values"></a>Determinar si un columna almacena los valores en mayúsculas o minúsculas
Esta sección enumeran las tareas de alto nivel que se realizarán en el sistema SAP para determinar si una columna de una tabla SAP almacena caracteres en mayúsculas o minúsculas. Para obtener instrucciones detalladas sobre cómo realizar esta tarea debe ponerse en contacto con el Administrador de SAP o consulte la documentación de SAP.  
  
### <a name="to-determine-the-case-of-values-stored-in-a-column"></a>Para determinar el caso de los valores almacenados en una columna  
  
1.  Inicie la GUI de SAP.  
  
2.  Vaya a la transacción SE37 y ejecute DDIF_TABL_GET.  
  
3.  Para el parámetro de nombre, especifique el nombre de tabla que contiene la columna para la que desea determinar la información del caso de carácter. Por ejemplo, KNA1.  
  
4.  El primer parámetro de tabla es DD03P_TAB. Haga clic en el parámetro para ver las filas de la tabla. Cada fila de esta tabla corresponde a una columna en la tabla (por ejemplo, KNA1) especificó en el paso 3.  
  
5.  En DD03P_TAB, busque el valor de la columna para cada fila en MINÚSCULAS. Si el valor de la columna en MINÚSCULAS es 'X', la columna correspondiente en la tabla (por ejemplo, KNA1), puede almacenar los caracteres en mayúsculas y minúsculas. Si el valor de la columna en MINÚSCULAS está vacío, la columna correspondiente sólo puede almacenar caracteres en mayúsculas.  
  
     Por ejemplo, para la fila de nombre minúscula columna es X. Por lo tanto, la columna NAME de KNA1 puede almacenar caracteres en mayúsculas y minúsculas. Sin embargo, para la fila de LAND1 minúscula columna está vacía. Por lo tanto, la columna LAND1 en KNA1 tabla solo puede almacenar caracteres en mayúsculas.  
  
## <a name="see-also"></a>Vea también  
 [Realizar tareas mediante la GUI de SAP para escenarios de adaptadores SAP específicos](../../adapters-and-accelerators/adapter-sap/performing-tasks-using-the-sap-gui-for-specific-sap-adapter-scenarios.md)