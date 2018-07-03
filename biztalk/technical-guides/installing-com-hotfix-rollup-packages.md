---
title: Instalación de paquetes acumulativos de revisiones de COM + | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 587ae3da-db65-4da8-9d3b-89effb91b197
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 110dced7d3931e1987ccf966efffb700e1c5555b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37020522"
---
# <a name="installing-com-hotfix-rollup-packages"></a>Instalación de paquetes acumulativos de revisiones de COM +
> [!NOTE]  
>  En este tema es aplicable sólo a Windows Server 2003.  
  
 Debe instalar la última versión del paquete de acumulativo de revisiones de COM + de Windows Server 2003 y la versión más reciente del paquete acumulativo de coordinador de transacciones distribuidas (DTC). Esto es porque los paquetes incluyen muchas correcciones de rendimiento y estabilidad.  
  
 Debe instalar estos paquetes acumulativos de actualizaciones en todos los equipos que ejecutan [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y en todos los equipos que ejecuten SQL Server. Los paquetes acumulativos son especialmente importantes para la solución de BizTalk funcionar bien en escenarios de alto rendimiento.  
  
 Los problemas DTC que se han corregido son los siguientes:  
  
- Cierre inesperado de DTC  
  
- Problemas de fragmentación de memoria  
  
- DTC puede dejar de responder bajo carga  
  
- DTC puede perder memoria o deje de responder cuando se usa con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]  
  
- Se ha mejorado el rendimiento de DTC bajo carga  
  
## <a name="installing-the-com-rollup-package"></a>Instalar el paquete de COM + paquete acumulativo de actualizaciones  
 COM + ya no está liberando paquetes acumulativos de actualizaciones. Siga esta información para instalar el último paquete de COM +:  
  
-   La versión final de la acumulación de COM + es la "Windows Server 2003 posterior al Service Pack 2 COM + 1.5 Hotfix Rollup paquete 12". Esta revisión se instalará en cualquier versión de Windows Server 2003, incluso aquellos sin un service pack instalado. Para obtener más información acerca de esta revisión puede encontrarse en el artículo de Microsoft Knowledge Base 934016, ["disponibilidad de Windows Server 2003 posterior al Service Pack 2 COM + 1.5 Hotfix Rollup paquete 12"](http://go.microsoft.com/fwlink/?LinkId=158756) (http://go.microsoft.com/fwlink/?LinkId=158756).  
  
## <a name="installing-the-dtc-rollup-package"></a>Instalar el paquete acumulativo de DTC  
 DTC lanzará paquetes acumulativos de actualizaciones independientes de COM +. Siga esta información para instalar el paquete más reciente de DTC:  
  
-   Cuando se redactó este documento, el último paquete acumulativo de revisiones DTC es "Paquete de 16". Para obtener más información acerca de esta revisión puede encontrarse en el artículo de Microsoft Knowledge Base 958013, ["Lista de los problemas de MS DTC que se han corregido en Windows Server 2003 MS DTC Hotfix Rollup Package 16"](http://support.microsoft.com/kb/979919) (http://support.microsoft.com/kb/979919).  
  
     El artículo de KB sobre el paquete de revisión DTC más reciente puede encontrarse mediante la búsqueda [ http://support.microsoft.com ](http://support.microsoft.com/) la frase (incluidas las comillas):  
  
    ```  
    "MS DTC Hotfix Rollup Package"  
    ```  
  
     La consulta siguiente realiza esta búsqueda para usted. Elija la última de ellas:  
  
     [http://support.microsoft.com/search/default.aspx?query="MS+DTC+Hotfix+Rollup+Package"](http://support.microsoft.com/search/default.aspx?query=%22MS+DTC+Hotfix+Rollup+Package%22)