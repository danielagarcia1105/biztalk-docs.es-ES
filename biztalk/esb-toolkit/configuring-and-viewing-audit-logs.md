---
title: Configurar y ver los registros de auditoría | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c725bf04-d59f-42c1-b327-b4268421689c
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 03c88e0a67a393b7ddc35ee8865d99d0299d41f2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22289844"
---
# <a name="configuring-and-viewing-audit-logs"></a>Configurar y ver los registros de auditoría
El Portal de administración de ESB mantiene un registro de auditoría de acciones que le ayudan a supervisar el uso y realizar un seguimiento de problemas. Los administradores pueden especificar los eventos que se escribirá el portal en el registro de auditoría.  
  
### <a name="to-view-the-audit-logs-for-the-portal"></a>Para ver los registros de auditoría para el portal  
  
1.  Seleccione el **administración** pestaña en el menú principal portal y, a continuación, haga clic en **Administrar registro de auditoría** para abrir el [página de registro de auditoría](../esb-toolkit/audit-log-page.md).  
  
2.  Para ver los detalles de reenvío y el mensaje original para los mensajes reenviados, haga clic en el identificador de un mensaje en la lista para abrir el registro de auditoría: página de Visor de mensajes.  
  
### <a name="to-configure-the-auditing-settings-for-the-portal"></a>Para configurar la configuración de auditoría para el portal  
  
1.  Asegúrese de que iniciar sesión en el portal mediante una cuenta que sea miembro del grupo de cuenta de administradores de BizTalk Server (de los cuales los administradores del portal están automáticamente miembro).  
  
2.  Seleccione el **administración** pestaña en el menú principal portal y, a continuación, haga clic en **configuración de error** para abrir el portal [página de configuración de error](../esb-toolkit/fault-settings-page.md).  
  
3.  Para cambiar las opciones de auditoría, seleccione las casillas de verificación en la **AuditOptions** sección para cada evento que desea auditar. Los eventos disponibles son la posibilidad de guardar la configuración modificada, reenvío correcto de un error después de modificarlo y error al volver a enviar un error.