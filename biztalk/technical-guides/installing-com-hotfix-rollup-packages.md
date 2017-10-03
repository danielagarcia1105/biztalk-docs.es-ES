---
title: "Instalación de paquetes acumulativos de revisiones de COM + | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 587ae3da-db65-4da8-9d3b-89effb91b197
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 40610c649e00993323adedf0ea29330dd289a0e3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="installing-com-hotfix-rollup-packages"></a>Instalación de paquetes acumulativos de revisiones de COM +
> [!NOTE]  
>  En este tema sólo es aplicable para Windows Server 2003.  
  
 Debe instalar la última versión del paquete de acumulativo de revisiones de COM + de Windows Server 2003 y la versión más reciente del paquete acumulativo de coordinador de transacciones distribuidas (DTC). Esto es porque los paquetes incluyen numerosas correcciones de rendimiento y estabilidad.  
  
 Debe instalar estos paquetes acumulativos en todos los equipos que ejecutan [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y en todos los equipos que ejecuten SQL Server. Los paquetes acumulativos son especialmente importantes para la solución de BizTalk funcionar bien en escenarios de alto rendimiento.  
  
 Los problemas DTC en el que se han corregido son los siguientes:  
  
-   Cierre inesperado de DTC  
  
-   Problemas de fragmentación de memoria  
  
-   DTC podría dejar de responder con carga  
  
-   DTC puede perder memoria o deje de responder cuando se usa con[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]  
  
-   Se ha mejorado el rendimiento de DTC de la carga  
  
## <a name="installing-the-com-rollup-package"></a>Instalar el paquete de COM + paquete acumulativo de actualizaciones  
 COM + ya no se está publicando paquetes acumulativos de actualizaciones. Siga estas indicaciones para instalar el último paquete de COM +:  
  
-   La versión final del resumen de COM + es el "Windows Server 2003 posteriores al Service Pack 2 COM + 1.5 revisión acumulación paquete 12". Esta revisión se instalará en cualquier versión de Windows Server 2003, incluso aquellos sin un service pack instalado. Para obtener más información acerca de esta revisión puede encontrarse en el artículo de Microsoft Knowledge Base 934016, ["disponibilidad de Windows Server 2003 posteriores al Service Pack 2 COM + 1.5 revisión acumulación paquete 12"](http://go.microsoft.com/fwlink/?LinkId=158756) (http://go.microsoft.com/fwlink/?LinkId=158756).  
  
## <a name="installing-the-dtc-rollup-package"></a>Instalar el paquete acumulativo DTC  
 DTC lanzarán paquetes acumulativos de independiente de COM +. Siga estas indicaciones para instalar el paquete más reciente de DTC:  
  
-   Cuando se redactó este documento, el último paquete acumulativo de revisiones DTC es "Paquete de 16". Para obtener más información acerca de esta revisión puede encontrarse en el artículo de Microsoft Knowledge Base 958013, ["Lista de los problemas de MS DTC que se corrigieron en Windows Server 2003 MS DTC paquete acumulativo de revisiones 16"](http://support.microsoft.com/kb/979919) (http://support.microsoft.com/kb/979919) .  
  
     El artículo de Knowledge Base sobre el paquete de paquete acumulativo de actualizaciones de revisión más reciente de DTC puede encontrarse mediante la búsqueda [http://support.microsoft.com](http://support.microsoft.com/) para la frase (incluidas las comillas):  
  
    ```  
    "MS DTC Hotfix Rollup Package"  
    ```  
  
     La siguiente consulta realiza esta búsqueda para usted. Elegir cuál es el más reciente:  
  
     [http://support.Microsoft.com/search/default.aspx?Query= "MS + DTC + + paquete acumulativo de revisiones +"](http://support.microsoft.com/search/default.aspx?query=%22MS+DTC+Hotfix+Rollup+Package%22)