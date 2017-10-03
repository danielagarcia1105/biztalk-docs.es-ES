---
title: Mostrar un EDI o informes de estado de AS2 | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 60968c3d-6329-411f-9f10-1dd4a6cc9d79
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0564a5c5d904a217ac406befebd3d7c742dc00c1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="displaying-an-edi-or-as2-status-report"></a>Mostrar un informe de estado de EDI o AS2
Al habilitar los informes de estado de EDI y AS2, tendrá acceso a los siguientes informes de estado:  
  
|Tipo de informe|Informe de estado de nivel superior|Informe de estado de nivel inferior|  
|--------------------|---------------------------------|--------------------------------|  
|ENRUTAMIENTO|Intercambio EDI y estado de confirmación correlacionado|-Detalles de la confirmación y del estado del intercambio<br /><br /> : Detalles del conjunto de transacciones<br /><br /> : Contenido del mensaje EDI|  
|ENRUTAMIENTO|Estado del lote|-|  
|ENRUTAMIENTO|Informe de agregación de intercambio|-|  
|ENRUTAMIENTO|Informe de agregación de conjunto de transacciones|-|  
|ENVÍO/RECEPCIÓN|Mensaje AS2 y estado de MDN correlacionado|Contenido de mensaje AS2|  
  
## <a name="prerequisites"></a>Requisitos previos  
 A continuación se exponen algunos requisitos previos para realizar el procedimiento de este tema:  
  
-   Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para personalizar los informes de estado.  
  
-   Si ha iniciado sesión como miembro del grupo de operadores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], puede mostrar informes de estado de solo lectura.  
  
## <a name="display-an-edi-or-as2-status-report"></a>Mostrar un informe de estado EDI o AS2  
  
1.  En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en el **grupo de BizTalk** nodo.  
  
2.  En el **concentrador de grupo** pestaña de la **información general del grupo** página de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, vaya a la parte inferior de la página.  
  
3.  Para mostrar la **intercambio EDI y estado de confirmación correlacionado** de informes, haga lo siguiente:  
  
    1.  Haga clic en **intercambio EDI y estado de confirmación correlacionado** en el **informes de estado de EDI** área no cliente de la **concentrador de grupo** ficha.  
  
    2.  Para ver los detalles de un intercambio y sus confirmaciones correlacionadas, haga clic en una entrada en los resultados de consulta de la **intercambio EDI y estado de confirmación correlacionado** de informes y, a continuación, haga clic en **confirmación y del estado de intercambio detalles**.  
  
    3.  Para ver los detalles de un conjunto de transacciones, cierre el intercambio confirmación y del estado informe de detalles, vuelva a la **intercambio EDI y estado de confirmación correlacionado** informe de detalles. Haga clic en una entrada en los resultados de la consulta y, a continuación, haga clic en **detalles de conjunto de transacciones**.  
  
    4.  Para ver los detalles acerca de los encabezados y la carga de un conjunto de transacciones, haga clic en una entrada en el **detalles de conjunto de transacciones** de informes y, a continuación, haga clic en **contenido de conjunto de transacciones de vista**.  
  
    5.  Para mostrar datos sobre el intercambio que contiene el conjunto de transacciones, haga clic en una entrada en el **detalles de conjunto de transacciones** de informes y, a continuación, haga clic en **estado de confirmación y del intercambio**. El intercambio que contiene el conjunto de transacciones se resaltará en el informe Estado de la confirmación y del intercambio.  
  
4.  Para mostrar la **estado del lote** de informes, haga lo siguiente:  
  
    1.  Haga clic en **estado del lote** en el **informes de estado de EDI** área no cliente de la **concentrador de grupo** ficha.  
  
    2.  Para mostrar los lotes completados asociados con una entrada por lotes en el **estado del lote** de informes, haga clic en la entrada y, a continuación, haga clic en **lotes completados**.  
  
    3.  Para mostrar datos de un intercambio por lotes completado, haga clic en el intercambio en el **lote completado** de informes y, a continuación, haga clic en **estado de confirmación y del intercambio**. La entrada del intercambio procesado por lotes se resaltará en el informe Estado de la confirmación y del intercambio.  
  
5.  Para mostrar la **informe de agregación de intercambio**, haga lo siguiente:  
  
    -   Haga clic en **informe de agregación de intercambio** en el **informes de estado de EDI** área no cliente de la **concentrador de grupo** ficha.  
  
6.  Para mostrar la **informe de agregación de conjunto de transacciones**, haga lo siguiente:  
  
    -   Haga clic en **informe de agregación de conjunto de transacciones** en el **informes de estado de EDI** área no cliente de la **concentrador de grupo** ficha.  
  
7.  Para mostrar la **mensaje AS2 y estado de MDN correlacionado** de informes, haga lo siguiente:  
  
    1.  Haga clic en **mensaje AS2 y estado de MDN correlacionado** en el **informes de estado de EDIINT** área no cliente de la **concentrador de grupo** ficha.  
  
    2.  Para mostrar el estado del intercambio EDI en un mensaje AS2, haga clic en una entrada en el **mensaje AS2 y estado de MDN correlacionado** de informes y, a continuación, haga clic en **estado de confirmación y del intercambio**.  
  
        > [!NOTE]
        >  Para obtener más información sobre cómo se correlacionan los Estados EDI y estado de AS2, vea la sección "Correlacionar un mensaje de AS2 con la carga de la EDI" de [mensaje AS2 y el informe de estado de MDN correlacionado](../core/as2-message-and-correlated-mdn-status-report.md).  
  
    3.  Para ver un mensaje AS2 en su formato, haga clic en una entrada en el informe de estado de AS2/MDN y, a continuación, haga clic en **formato del mensaje**.  
  
    4.  Para mostrar un mensaje AS2 en formato descodificado, haga clic en una entrada en el informe de estado de AS2/MDN y, a continuación, haga clic en **formato de mensaje descodificado**.  
  
    5.  Para mostrar un mensaje MDN, haga clic en una entrada en el informe de estado de AS2/MDN y, a continuación, haga clic en **mensaje Mdn**.  
  
## <a name="see-also"></a>Vea también  
 [Supervisión de soluciones EDI y AS2](../core/monitoring-edi-and-as2-solutions.md)   
 [EDI y AS2 informes de estado](../core/edi-and-as2-status-reporting.md)   
 [Habilitar informes de estado de AS2 y EDI](../core/enabling-edi-and-as2-status-reports.md)   
 [Configurar un informe de estado de AS2 y EDI](../core/configuring-an-edi-and-as2-status-report.md)