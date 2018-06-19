---
title: Reparar y volver a enviar un mensaje | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ccd720b4-44a2-4c44-bf6e-8cf5e9ded1aa
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e524ffca1b79032dce55f74e195032d14ec1bf9e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22295060"
---
# <a name="repairing-and-resubmitting-a-message"></a>Reparar y volver a enviar un mensaje
Para reparar y volver a enviar un mensaje de error, use la página de errores del Portal de administración de ESB.  
  
### <a name="to-repair-and-resubmit-a-message-for-processing"></a>Reparar y volver a enviar un mensaje para el procesamiento  
  
1.  Busque el mensaje de error deseada en el [Portal errores de página](../esb-toolkit/portal-faults-page.md) página del Portal de administración de ESB. Use las capacidades de filtrado en la página de errores para buscar un mensaje específico. Deje cualquiera de los controles en blanco para recuperar todos los mensajes. Tenga en cuenta que el filtrado en una base de datos de errores muy grandes puede tardar varios segundos para mostrar los resultados adecuados. La figura 1 muestra la página de errores.  
  
     ![FaultsPage](../esb-toolkit/media/faultspage.gif "FaultsPage")  
  
     **Figura 1**  
  
     **La página de errores del Portal de administración de ESB**  
  
2.  Haga clic en cualquier parte en la fila del mensaje de error deseada para abrir la [Visor de mensajes de error de Portal](../esb-toolkit/portal-fault-message-viewer.md) página [vista de detalles de error](../esb-toolkit/fault-details-view.md).  
  
3.  Desplácese hasta la parte inferior de la vista de detalles del error a la lista de mensajes contenidos en el mensaje de error. La figura 2 muestra la **mensajes** sección de la página del Visor de error.  
  
     ![Mensajes de sección](../esb-toolkit/media/ch8-messagessection.gif "Ch8-MessagesSection")  
  
     **Figura 2**  
  
     **La sección de mensajes de la página de error Visor del Portal de administración de ESB**  
  
4.  Haga clic en el identificador del mensaje del mensaje que desea reenviar. Se abrirá el mensaje en [vista Detalles de mensajes](../esb-toolkit/message-details-view.md), que muestra los detalles del mensaje individual y el contenido del mensaje, como se muestra en la figura 3.  
  
     ![Visor de mensajes](../esb-toolkit/media/ch8-messageviewer.gif "Ch8-MessageViewer")  
  
     **Figura 3**  
  
     **La página del Visor de mensajes del Portal de administración de ESB**  
  
5.  Haga clic en el **editar** vínculo que figura en el cuadro de texto que contiene el contenido del mensaje para cambiar a modo de edición y, a continuación, edite el contenido del mensaje según sea necesario. Por ejemplo, necesite cambiar los parámetros para las invocaciones de método de servicio dentro del mensaje. Tenga en cuenta que debe cumplir el estilo de documento nativo (por ejemplo, formato de archivo sin formato o XML) para evitar el rechazo del mensaje cuando se vuelven a enviar. Figura 4 se ilustran la **detalles del mensaje** sección de la página Editor de mensajes.  
  
     ![Detalles del mensaje](../esb-toolkit/media/ch8-messagedetails.gif "Ch8-MessageDetails")  
  
     **Figura 4**  
  
     **La sección de detalles del mensaje de la página del Visor de mensajes del Portal de administración de ESB**  
  
6.  Después de editar el mensaje, seleccione una ubicación de reenvío en la lista desplegable en el cuadro de texto de mensaje. Esta lista muestra la lista dinámicamente recuperada de los extremos disponibles. Debe seleccionar un extremo configurado como un punto de conexión de reenvío. Los siguientes extremos son adecuados para reenvío:  
  
    -   **WCF en rampa**. Este extremo es la servicios WCF de ESB itinerario en rampa y solo está disponible para archivos XML. El archivo Web.config portal define la dirección URL para este aumento.  
  
    -   **SOAP en rampa**. Este extremo es la servicios ASMX de ESB itinerario en rampa y solo está disponible para archivos XML. El archivo Web.config portal define la dirección URL para este aumento.  
  
    -   **Cualquier ubicación de recepción mediante el adaptador de HTTP de BizTalk**. Esta opción está disponible para los archivos XML y archivos sin formato.  
  
7.  Haga clic en el **reenviar** vínculo para volver a enviar el mensaje. Un mensaje que indica la **estado de reenvío** aparece en el cuadro de texto del contenido del mensaje.  
  
8.  Si es necesario, abra el [página de registro de auditoría](../esb-toolkit/audit-log-page.md) desde el **administrador** para confirmar el reenvío de mensajes, como se muestra en la figura 5.  
  
     ![Vista de página auditlog de tamaño reducido](../esb-toolkit/media/ch8-auditlogpagesmallview.gif "Ch8-AuditLogPageSmallView")  
  
     **Figura 5**  
  
     **La página de registro de auditoría del Portal de administración de ESB**