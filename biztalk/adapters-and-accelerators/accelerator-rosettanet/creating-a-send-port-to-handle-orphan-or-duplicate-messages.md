---
title: "Crear un puerto de envío para controlar los mensajes duplicados o huérfanas | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, duplicate messages
- messages, orphaned messages
- send ports, duplicate messages
- send ports, orphaned messages
- messages, send ports
ms.assetid: 61d51206-13e3-4d32-a184-866248db9b45
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d9a5e52197c81e86bac69603e72d294cfbcd6faa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="creating-a-send-port-to-handle-orphan-or-duplicate-messages"></a>Crear un puerto de envío para que procese huérfano o mensajes duplicados
En este tema se describe cómo configurar un puerto de envío que puede usar para eliminar mensajes duplicados o huérfanas.  
  
 Huérfano o mensajes duplicados pueden ser un problema si [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] recibe copias adicionales de un mensaje después de la orquestación de proceso público completó el procesamiento de la primera copia del mensaje. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]marca los mensajes duplicados y suspenderá. Puede ver estos mensajes en la consola de administración de BizTalk. Para obtener más información acerca de la consola de administración de BizTalk, vea "Utilizar la consola de administración de BizTalk" en la [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] ayuda.  
  
 Huérfano o mensajes duplicados permanecen en la consola de administración de BizTalk hasta que se revise o eliminarlos. La manera más eficaz de la eliminación de ellos consiste en configurar un puerto de envío con filtros de huérfano o mensajes duplicados. Puede moverlos mediante los medios de transporte disponible en [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)]. Por ejemplo, puede mover mediante el uso de transporte de archivo. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]envía los mensajes duplicados o huérfanas como archivos en una ubicación de un disco duro. Esto permite eliminarlos fácilmente. El puerto puede estar en la dada de alta y detenido estado, en el que se mostrará caso todos los mensajes enviados a él como suspendida en ese puerto de envío.  
  
> [!NOTE]
>  En lugar de crear un puerto de envío para procesar los mensajes duplicados y huérfanas, puede crear un componente de canalización especial para eliminar estos mensajes de la base de datos de cuadro de mensajes. Puede usar el componente FixMsg en la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] SDK como una plantilla. Tiene que modificar el `IComponent.Execute` método devuelva un valor null. Esto hace que [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] para descartar cualquier mensaje enviado a una canalización que contiene el componente. Tendrá que compilar este componente de canalización y agregarlo a una canalización de envío y, a continuación, compilar, implementar y seleccione la canalización de envío para el puerto de receptor. Para obtener más información, vea "CustomComponent ([!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] ejemplo)" en [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] ayuda.  
  
### <a name="to-create-a-send-port-to-handle-orphan-or-duplicate-messages"></a>Para crear un puerto de envío para que procese huérfano o mensajes duplicados  
  
1.  En [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], en la **vista** menú, haga clic en **el Explorador de BizTalk**.  
  
2.  En el Explorador de BizTalk, expanda **base de datos de administración de BizTalk**y, a continuación, expanda **puertos de envío**.  
  
3.  Haga clic con el botón secundario en **Puertos de envío**y seleccione **Agregar puerto de envío**.  
  
4.  En la ventana Crear nuevo puerto de envío, seleccione **Puerto unidireccional estático**y, a continuación, haga clic en **Aceptar**.  
  
5.  En la ventana Propiedades de puerto de envío de unidireccional estático, en la **nombre** , escriba un nombre para el puerto de envío.  
  
6.  En el panel izquierdo, haga clic en **transporte**. En el panel derecho, haga clic en **tipo de transporte**y seleccione **archivo** para el tipo de transporte. Haga clic en el botón de puntos suspensivos (...) junto a **dirección (URI)**, escriba una ubicación en el disco duro y, a continuación, haga clic en **Aceptar**.  
  
7.  En el panel izquierdo, haga clic en **enviar**, haga clic en **canalización de envío**y, a continuación, seleccione **Microsoft.BizTalk.DefaultPipelines.PassThruTransmit**.  
  
8.  En el panel izquierdo, haga clic en **filtra y asigna**y, a continuación, haga clic en **filtros**.  
  
9. En la primera línea en el panel derecho, para **propiedad**, seleccione **Microsoft.Solutions.BTARN.GlobalSchemas.IsDuplicateMessage** en la lista desplegable, deje el **operador**como  **==** , escriba **True** para **valor**y, a continuación, seleccione **o** en la lista desplegable de  **Grupo**.  
  
10. En la segunda línea en el panel derecho, para **propiedad**, seleccione **Microsoft.Solutions.BTARN.GlobalSchemas.IsOrphanMessage** en la lista desplegable, deje el **operador**como  **==** y, a continuación, escriba **True** para **valor**.  
  
11. Haga clic en **Aceptar**.  
  
12. En el Explorador de BizTalk, haga clic en el nombre del puerto de envío, haga clic en **dar de alta**. Después de que se ha dado de alta el puerto de envío, haga clic en el puerto de envío y, a continuación, haga clic en **iniciar**.  
  
## <a name="see-also"></a>Vea también  
 [Guía de programación](../../adapters-and-accelerators/accelerator-rosettanet/programming-guide2.md)