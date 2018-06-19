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
# <a name="configuring-and-viewing-audit-logs"></a><span data-ttu-id="d296c-102">Configurar y ver los registros de auditoría</span><span class="sxs-lookup"><span data-stu-id="d296c-102">Configuring and Viewing Audit Logs</span></span>
<span data-ttu-id="d296c-103">El Portal de administración de ESB mantiene un registro de auditoría de acciones que le ayudan a supervisar el uso y realizar un seguimiento de problemas.</span><span class="sxs-lookup"><span data-stu-id="d296c-103">The ESB Management Portal maintains an audit log of actions that help you to monitor usage and track problems.</span></span> <span data-ttu-id="d296c-104">Los administradores pueden especificar los eventos que se escribirá el portal en el registro de auditoría.</span><span class="sxs-lookup"><span data-stu-id="d296c-104">Administrators can specify which events the portal will write to the audit log.</span></span>  
  
### <a name="to-view-the-audit-logs-for-the-portal"></a><span data-ttu-id="d296c-105">Para ver los registros de auditoría para el portal</span><span class="sxs-lookup"><span data-stu-id="d296c-105">To view the audit logs for the portal</span></span>  
  
1.  <span data-ttu-id="d296c-106">Seleccione el **administración** pestaña en el menú principal portal y, a continuación, haga clic en **Administrar registro de auditoría** para abrir el [página de registro de auditoría](../esb-toolkit/audit-log-page.md).</span><span class="sxs-lookup"><span data-stu-id="d296c-106">Point to the **Admin** tab on the portal main menu, and then click **Manage Audit Log** to open the [Audit Log Page](../esb-toolkit/audit-log-page.md).</span></span>  
  
2.  <span data-ttu-id="d296c-107">Para ver los detalles de reenvío y el mensaje original para los mensajes reenviados, haga clic en el identificador de un mensaje en la lista para abrir el registro de auditoría: página de Visor de mensajes.</span><span class="sxs-lookup"><span data-stu-id="d296c-107">To see the resubmission details and the original message for resubmitted messages, click the identifier of a message in the list to open the Audit Log – Message Viewer page.</span></span>  
  
### <a name="to-configure-the-auditing-settings-for-the-portal"></a><span data-ttu-id="d296c-108">Para configurar la configuración de auditoría para el portal</span><span class="sxs-lookup"><span data-stu-id="d296c-108">To configure the auditing settings for the portal</span></span>  
  
1.  <span data-ttu-id="d296c-109">Asegúrese de que iniciar sesión en el portal mediante una cuenta que sea miembro del grupo de cuenta de administradores de BizTalk Server (de los cuales los administradores del portal están automáticamente miembro).</span><span class="sxs-lookup"><span data-stu-id="d296c-109">Ensure that you log on to the portal using an account that is a member of the BizTalk Server Administrators account group (of which portal administrators are automatically a member).</span></span>  
  
2.  <span data-ttu-id="d296c-110">Seleccione el **administración** pestaña en el menú principal portal y, a continuación, haga clic en **configuración de error** para abrir el portal [página de configuración de error](../esb-toolkit/fault-settings-page.md).</span><span class="sxs-lookup"><span data-stu-id="d296c-110">Point to the **Admin** tab on the portal main menu, and then click **Fault Settings** to open the portal [Fault Settings Page](../esb-toolkit/fault-settings-page.md).</span></span>  
  
3.  <span data-ttu-id="d296c-111">Para cambiar las opciones de auditoría, seleccione las casillas de verificación en la **AuditOptions** sección para cada evento que desea auditar.</span><span class="sxs-lookup"><span data-stu-id="d296c-111">To change the auditing options, select the check boxes in the **AuditOptions** section for each event you want to audit.</span></span> <span data-ttu-id="d296c-112">Los eventos disponibles son la posibilidad de guardar la configuración modificada, reenvío correcto de un error después de modificarlo y error al volver a enviar un error.</span><span class="sxs-lookup"><span data-stu-id="d296c-112">The available events are the saving of modified settings, successful resubmission of a fault after editing, and failure when resubmitting a fault.</span></span>