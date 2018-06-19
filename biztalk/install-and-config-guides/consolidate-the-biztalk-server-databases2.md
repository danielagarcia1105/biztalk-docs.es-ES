---
title: Consolidar el servidor BizTalk Server Databases2 | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d7fc4fe6-3fc2-4164-9f16-90b6f473ba8c
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 56a8f594298569caaa4842a5f754ba991e9e5f51
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22296324"
---
# <a name="consolidate-the-biztalk-server-databases2"></a>Consolidar las bases de datos de BizTalk Server2
Es posible que una instalación de Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] necesite que se creen hasta 13 bases de datos diferentes en Microsoft [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] para usarlas como almacenes de datos de las diversas características de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Debido a la sobrecarga necesaria para administrar y mantener estas bases de datos, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] permite consolidar varias bases de datos en una sola. En esta sección se describe cómo llevar a cabo la consolidación de bases de datos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y se explican cuestiones sobre la implementación de la consolidación de bases de datos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
> [!NOTE]
>  Para obtener una lista completa de todas las bases de datos que son necesarias al instalar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], consulte [Bases de datos en BizTalk Server](../core/databases-in-biztalk-server.md).  
  
## <a name="implementing-biztalk-database-consolidation"></a>Implementar la consolidación de bases de datos de BizTalk  
 La consolidación de base de datos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] se realiza después de la instalación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], durante la configuración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Siga los pasos que se detallan a continuación para implementar la consolidación de base de datos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  
  
1.  Haga clic en **Inicio**, **Programas**, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y, después, en **Configuración de BizTalk Server**. Si se le pide que seleccione un tipo de configuración, haga clic en **Configuración personalizada**.  
  
2.  Especifique el mismo **nombre de servidor** y **nombre de base de datos** de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] (por ejemplo, *BizTalkConsolidatedDb*) para uno o varios de los siguientes almacenes de datos:  
  
    |Nombre de la característica|Nombre de almacén de datos|  
    |------------------|---------------------|  
    |SSO empresarial|Base de datos de SSO|  
    |Grupo|Base de datos de administración de BizTalk|  
    |Grupo|Base de datos de cuadro de mensajes de BizTalk|  
    |Grupo|Base de datos de seguimiento de BizTalk|  
    |motor de reglas de negocios|Base de datos de motor de reglas|  
  
     Tenga en cuenta que los siguientes almacenes de datos **no** deberían configurarse para compartir una base de datos de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]:  
  
    |Nombre de la característica|Nombre de almacén de datos|  
    |------------------|---------------------|  
    |Herramientas de BAM|Base de datos de importación principal de BAM|  
    |Herramientas de BAM|Base de datos de archivo de BAM|  
  
3.  Establezca las opciones de configuración restantes y aplique la configuración. La herramienta de configuración creará tablas en la base de datos de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] compartida para los almacenes de datos para los que ha especificado el mismo **Nombre del servidor** y **Nombre de la base de datos** de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].  
  
## <a name="considerations-for-implementing-biztalk-database-consolidation"></a>Consideraciones sobre la implementación de la consolidación de bases de datos de BizTalk  
 Tenga en cuenta lo siguiente cuando consolide una base de datos de BizTalk:  
  
1.  La consolidación de base de datos reduce la sobrecarga que se suele producir en la administración y el mantenimiento de las bases de datos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] aunque sólo debería implementarse en el entorno adecuado. Antes de implementar la consolidación de base de datos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en un entorno de producción, debería medirse el efecto sobre el rendimiento constante de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en un entorno de ensayo. Estudie la implementación de la consolidación de base de datos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] como medio para simplificar la administración y el mantenimiento de bases de datos en los escenarios siguientes:  
  
    -   Entornos de producción de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] de pequeña escala y bajo volumen en los que no es muy probable que se produzcan atascos de rendimiento de base de datos.  
  
    -   Entornos de producción de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] de escala y volumen medios si la base de datos de seguimiento de BizTalk no se incluye en la consolidación y si, de forma idónea, la base de datos de seguimiento de BizTalk se crea en un disco físico diferente al disco donde se encuentra la base de datos consolidada.  
  
    -   Entornos de producción de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] de gran escala y volumen elevado si la base de datos de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] compartida se encuentra físicamente en un dispositivo de red de área de almacenamiento (SAN) de alto rendimiento en el que hay muy poca probabilidad de que se produzca un atasco de rendimiento.  
  
    -   Entornos de desarrollo o de prueba de concepto en los que el rendimiento de la base de datos es una preocupación secundaria.  
  
2.  El rendimiento global de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] suele depender del rendimiento de las bases de datos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Por tanto, la consolidación de base de datos no debería implementarse en ningún entorno de producción de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] con un volumen elevado actual o futuro. La excepción son las bases de datos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] que se encuentran físicamente en un dispositivo de red de área de almacenamiento (SAN) de alto rendimiento en el que hay muy poca probabilidad de que se produzca un atasco de rendimiento. Si los discos de la base de datos no se encuentran en una red de este tipo, las bases de datos distribuidas proporcionan mayor rendimiento para las bases de datos consolidadas, en particular en condiciones de carga.  
  
3.  Si la base de datos de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] se incluye en la consolidación de base de datos y la base de datos de consolidación no se llama **BizTalkMgmtDb**, la consola de administración de BizTalk debe configurarse para que seleccione la base de datos de consolidación. Siga los pasos indicados en [Cómo efectuar una conexión a un grupo existente](../core/how-to-connect-to-an-existing-group.md) y configure la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para que apunte a la base de datos de consolidación con el fin de administrar el grupo de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
4.  Para obtener más información sobre el rendimiento constante de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], consulte [Planear el rendimiento mantenido](../core/planning-for-sustained-performance.md).  
  
 Para obtener más información sobre las actividades relacionadas con el mantenimiento de las bases de datos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], consulte [Mantener BizTalk Server1](../core/maintaining-biztalk-server1.md).