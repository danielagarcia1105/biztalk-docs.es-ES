---
title: Creación de un puerto de envío para controlar mensajes huérfanos o duplicados | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, duplicate messages
- messages, orphaned messages
- send ports, duplicate messages
- send ports, orphaned messages
- messages, send ports
ms.assetid: 61d51206-13e3-4d32-a184-866248db9b45
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fc4e6e8650f0da1446a48b5da8c8f7c2142af7bb
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997901"
---
# <a name="creating-a-send-port-to-handle-orphan-or-duplicate-messages"></a>Creación de un puerto de envío para controlar mensajes huérfanos o duplicados
Este tema describe cómo configurar un puerto de envío que puede usar para eliminar mensajes huérfanos o duplicados.  
  
 Mensajes huérfanos o duplicados pueden ser un problema si Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] recibe copias adicionales de un mensaje después de la orquestación de proceso público ha completado el procesamiento de la primera copia del mensaje. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] marca los mensajes como duplicados y se suspenderá. Puede ver estos mensajes en la consola de administración de BizTalk. Para obtener más información acerca de la consola de administración de BizTalk, consulte "Uso de la consola de administración de BizTalk" en la Ayuda de BizTalk Server.  
  
 Mensajes huérfanos o duplicados permanecen en la consola de administración de BizTalk hasta que se revise o eliminarlos. La manera más eficaz de la eliminación de ellas es configurar un puerto de envío con los filtros configurados para mensajes huérfanos o duplicados. Puede moverlos con ningún medio de transporte disponibles en BizTalk Server. Por ejemplo, puede mover con el transporte de archivo. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] envía los mensajes huérfanos o duplicados como archivos en una ubicación de un disco duro. Esto le permite eliminar ellos fácilmente. El puerto puede estar en el inscrito detenido estado y, en el que caso todos los mensajes se envían a la se mostrará como suspendido en ese puerto de envío.  
  
> [!NOTE]
>  En lugar de crear un puerto de envío para controlar los mensajes huérfanos o duplicados, puede crear un componente de canalización especial para eliminar estos mensajes de la base de datos de cuadro de mensajes. Puede usar el componente FixMsg en la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] SDK como plantilla. Tiene que modificar el `IComponent.Execute` método devuelva null. Esto hace que [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] para descartar los mensajes enviados a una canalización que contiene el componente. Tendrá que compilar este componente de canalización y agregarlo a una canalización de envío y, a continuación, compilar, implementar y seleccione la canalización de envío para el puerto de receptor. Para obtener más información, vea "CustomComponent ([!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] ejemplo)" en la Ayuda de BizTalk Server.  
  
### <a name="to-create-a-send-port-to-handle-orphan-or-duplicate-messages"></a>Para crear un puerto de envío para controlar mensajes huérfanos o duplicados  
  
1. En [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], en el **vista** menú, haga clic en **el Explorador de BizTalk**.  
  
2. En el Explorador de BizTalk, expanda **base de datos de administración de BizTalk**y, a continuación, expanda **puertos de envío**.  
  
3. Haga clic con el botón secundario en **Puertos de envío**y seleccione **Agregar puerto de envío**.  
  
4. En la ventana Crear nuevo puerto de envío, seleccione **Puerto unidireccional estático**y, a continuación, haga clic en **Aceptar**.  
  
5. En la ventana Propiedades de puerto de envío de unidireccional estático, en el **nombre** , escriba un nombre para el puerto de envío.  
  
6. En el panel izquierdo, haga clic en **transporte**. En el panel derecho, haga clic en **tipo de transporte**y seleccione **archivo** para el tipo de transporte. Haga clic en el botón de puntos suspensivos (...) junto a **dirección (URI)**, escriba una ubicación en el disco duro y, a continuación, haga clic en **Aceptar**.  
  
7. En el panel izquierdo, haga clic en **enviar**, haga clic en **canalización de envío**y, a continuación, seleccione **Microsoft.BizTalk.DefaultPipelines.PassThruTransmit**.  
  
8. En el panel izquierdo, haga clic en **filtra y asigna**y, a continuación, haga clic en **filtros**.  
  
9. En la primera línea en el panel derecho, para **propiedad**, seleccione **Microsoft.Solutions.BTARN.GlobalSchemas.IsDuplicateMessage** en la lista desplegable, deje el **operador**como **==**, escriba **True** para **valor**y, a continuación, seleccione **o** en la lista desplegable para  **Grupo**.  
  
10. En la segunda línea en el panel derecho, para **propiedad**, seleccione **Microsoft.Solutions.BTARN.GlobalSchemas.IsOrphanMessage** en la lista desplegable, deje el **operador**como **==** y, a continuación, escriba **True** para **valor**.  
  
11. Haga clic en **Aceptar**.  
  
12. En el Explorador de BizTalk, haga clic en el nombre del puerto de envío, haga clic en **Enlist**. Después de que ha dado de alta el puerto de envío, haga clic en el puerto de envío y, a continuación, haga clic en **iniciar**.  
  
## <a name="see-also"></a>Vea también  
 [Guía de programación](../../adapters-and-accelerators/accelerator-rosettanet/programming-guide2.md)