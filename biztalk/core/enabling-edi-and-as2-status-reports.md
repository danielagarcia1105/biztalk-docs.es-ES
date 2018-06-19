---
title: Habilitar informes de estado de AS2 y EDI | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: aa40fbad-51ad-40e0-9fe3-68e54beb11a5
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cef3d25040c253badd0f517326cc7830b6962df8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22242916"
---
# <a name="enabling-edi-and-as2-status-reports"></a>Habilitar informes de estado de AS2 y EDI
Este tema describe cómo configurar los informes de estado EDI y AS2 en el **información general del grupo** página de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
 Los datos de seguimiento de los informes de estado se guardan en la base de datos de seguimiento de BizTalk (BizTalkDTADb), según las propiedades de almacenamiento seleccionadas en los procedimientos que figuran a continuación. Puede configurar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para habilitar los informes de estado para cada acuerdo. En función de la cantidad de datos que se almacenen, deben archivarse periódicamente los datos del almacén activo y, en última instancia, eliminarse del almacén de archivado, según convenga. Para obtener más información acerca de cómo administrar la base de datos de BizTalkDTADb, consulte [archivar y purgar la base de datos de seguimiento de BizTalk](../core/archiving-and-purging-the-biztalk-tracking-database.md).  
  
 Puede habilitar los informes de estado de tres formas:  
  
-   Habilitar los informes de estado para los intercambios EDI entrantes o salientes que se resolvieron en un acuerdo.  
  
-   Habilitar los informes de estado para las propiedades del acuerdo de reserva EDI, de modo que el informe de estado esté activado para intercambios EDI para los que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no pudo determinar ningún acuerdo.  
  
-   Habilitar informes de estado para mensajes AS2  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe haber iniciado la sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o del grupo de operadores de BizTalk Server B2B.  
  
### <a name="to-enable-edi-status-reports-for-an-agreement"></a>Procedimiento para habilitar informes de estado de EDI para un acuerdo  
  
1.  En el  **[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración** consola, haga clic en el **partes** nodo bajo el [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)] y **grupo de BizTalk** nodos.  
  
2.  En el **entidades y perfiles empresariales** panel, haga clic en la entidad que tenga el acuerdo de X12 o EDIFACT para el que desea habilitar los informes de estado.  
  
3.  En el **contratos** sección, haga clic en el contrato para el que desea habilitar los informes de estado y, a continuación, haga clic en **propiedades**.  
  
4.  En el **General** ficha la **configuración de Host común** sección, haga clic en **activar informes**.  
  
    > [!NOTE]
    >  Este paso especifica las entradas de los mensajes en la interfaz de usuario de informes de estado de la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
5.  Seleccione **almacenar carga y conjunto de transacciones para los informes** almacenar transacciones se establece en las tablas EDI de la base de datos de seguimiento (BizTalkDTADb).  
  
    > [!NOTE]
    >  Si habilita el almacenamiento de conjuntos de transacciones mientras una instancia de la orquestación de procesamiento por lotes está activada, no se almacenarán los conjuntos de transacciones para el lote que se está creando. Sin embargo, si deshabilita el almacenamiento de conjuntos de transacciones mientras una instancia del procesamiento por lotes esté activada, se deshabilitará el almacenamiento en mitad del procesamiento por lotes.  
  
6.  Haga clic en **Aceptar**.  
  
7.  Reinicie el servicio BizTalk (en el cuadro de diálogo Administración de equipos). Si se utiliza la canalización AS2EdiReceive o la canalización AS2EdiSend en la solución, reinicie el servicio de administración de IIS (mediante la *iisreset* comando), así como.  
  
    > [!NOTE]
    >  El servicio de BizTalk necesita reiniciarse después de que se haya activado o desactivado el informe de estado de EDI para que se aplique el cambio. Si se está utilizando la canalización AS2EdiReceive o AS2EdiSend en la solución, el servicio de BizTalk y el servicio IIS deben reiniciarse para que se aplique el cambio. Tenga en cuenta que esto no es necesario al habilitar el informe de estado de AS2.  
  
### <a name="to-enable-edi-status-reports-for-fallback-agreements"></a>Para habilitar los informes de estado de EDI para acuerdos de reserva  
  
1.  En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda **grupo de BizTalk** nodos, haga clic en **partes**y seleccione **X12 configuración de reserva**o **configuración de reserva de EDIFACT**.  
  
    > [!NOTE]
    >  Al configurar los informes de estado en los acuerdos de reserva, la configuración únicamente se aplica cuando no se ha determinado ningún acuerdo para un mensaje.  
  
2.  En el **páginas generales de configuración de reserva** , haga clic en **activar informes de EDI**.  
  
    > [!NOTE]
    >  Este paso especifica las entradas de los mensajes en la interfaz de usuario de informes de estado de la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
3.  Seleccione **almacenar carga y conjunto de transacciones para los informes** almacenar transacciones se establece en las tablas EDI de la base de datos de seguimiento (BizTalkDTADb).  
  
    > [!NOTE]
    >  **Para mensajes codificados en EDIFACT**: Si selecciona esta propiedad, también debe seleccionar un valor para el campo UNB3.2 (calificador de código) en la página de definición de segmento UNB del cuadro de diálogo Propiedades globales de EDI. Esta propiedad no se establece de forma predeterminada y el intercambio se suspenderá si **almacenar carga y conjunto de transacciones para los informes** está seleccionada, pero no se selecciona ningún valor para UNB3.2.  
  
4.  Haga clic en **Aceptar**.  
  
### <a name="to-enable-as2-status-reports"></a>Para habilitar informes de estado de AS2  
  
1.  En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, en la [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)] y **grupo de BizTalk** nodos, haga clic en el **partes** nodo.  
  
2.  En el **entidades y perfiles empresariales** panel, haga clic en la entidad que tenga el acuerdo de X12 o EDIFACT para el que desea habilitar los informes de estado.  
  
3.  En el **contratos** sección, haga clic en el contrato para el que desea habilitar los informes de estado y, a continuación, haga clic en **propiedades**.  
  
4.  En el **configuración de Host común** sección, haga clic en **activar informes**.  
  
    > [!NOTE]
    >  Este paso especifica las entradas de los mensajes en la interfaz de usuario de informes de estado de la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
5.  En la ficha de acuerdo unidireccional del **propiedades del acuerdo de** cuadro de diálogo, haga clic en el **seguimiento de mensaje de receptor (NRR)** página.  
  
6.  En el **seguimiento de mensaje de receptor (NRR)** página, haga clic en **NRR habilitado para mensajes AS2 codificados de entrada** para habilitar la visualización del formato de los de los mensajes entrantes.  
  
    > [!NOTE]
    >  El formato del mensaje se mostrará cuando haga clic en el mensaje en el mensaje AS2 y la página de estado de MDN correlacionado y, a continuación, haga clic en **formato del mensaje**.  
  
    > [!NOTE]
    >  El **activar informes** propiedad se debe seleccionar para que habilitar el almacenamiento de datos en la base de datos sin repudio. Si selecciona esta o cualquiera de las demás propiedades que habilitan el almacenamiento en la base de datos de no repudio, se mostrará un mensaje emergente pidiéndole que active los informes de AS2. Si hace clic en **Sí**, informes de AS2 se activará automáticamente.  
  
7.  En el **seguimiento de mensaje de receptor (NRR)** página, haga clic en **NRR habilitado para mensajes AS2 entrantes descodificados** para habilitar la visualización del formato descodificado de los mensajes entrantes.  
  
8.  En el **seguimiento de mensaje de receptor (NRR)** página, haga clic en **NRR habilitado para MDN de salida** para habilitar la visualización de respuestas MDN para los mensajes entrantes.  
  
9. En la ficha de acuerdo unidireccional del **propiedades del acuerdo de** cuadro de diálogo, haga clic en el **seguimiento de mensaje de remitente (NRR)** página.  
  
10. En el **seguimiento de mensaje de remitente (NRR)** página, haga clic en **NRR habilitado para mensajes AS2 salientes codificados** para habilitar la visualización del formato de los mensajes salientes.  
  
11. En el **seguimiento de mensaje de remitente (NRR)** página, haga clic en **NRR habilitado para mensajes AS2 salientes descodificados** para habilitar la visualización del formato descodificado de los mensajes salientes.  
  
12. En el **seguimiento de mensaje de remitente (NRR)** página, haga clic en **NRR habilitado para MDN de entrada** para habilitar la visualización de respuestas MDN para mensajes salientes.  
  
13. Haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
 [Supervisión de soluciones EDI y AS2](../core/monitoring-edi-and-as2-solutions.md)   
 [Configurar un informe de estado de AS2 y EDI](../core/configuring-an-edi-and-as2-status-report.md)   
 [EDI y AS2 informes de estado](../core/edi-and-as2-status-reporting.md)   