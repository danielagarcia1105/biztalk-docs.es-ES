---
title: Ejemplo FileTransport | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a32c8cbf-0c17-4237-b2a3-9d21faa13496
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 495e4cfe4c9c9b9d7ae16ee58f7831ad5447d37b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="filetransport-sample"></a>Ejemplo de FileTransport
El ejemplo FileTransport muestra cómo configurar [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] utilice puertos de archivo, en lugar de los puertos SQL. El ejemplo FileTransport usa el protocolo de transferencia de archivos (FTP) para enviar y recibir mensajes, en lugar de HTTP.  
  
> [!NOTE]
>  Este documento se da por supuesto que está instalando [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] prueba o demostración sólo por motivos internos. No recomiendan cualquier cuenta de seguridad mínima o configurar. Debe usar una cuenta que tenga permisos administrativos locales a lo largo de los procedimientos de este tema.  
  
> [!NOTE]
>  Este ejemplo no es compatible con los datos adjuntos del mensaje.  
  
## <a name="filetransport-binding-files"></a>Archivos de enlace de FileTransport  
 El ejemplo de FileTransport incluye dos archivos de enlace. Puede utilizar cada uno de estos archivos de enlace para configurar los puertos de archivo para su uso con una orquestación de BTARN. Estos archivos de enlace se encuentran en  *\<unidad >*: \Program BizTalk \<versión > Accelerator for RosettaNet \SDK\FileTransport. Abra cada archivo de enlace en un editor como el Bloc de notas para ver la configuración de la orquestación, puerto de envío, puerto de recepción y ubicación de recepción, como se muestra a continuación.  
  
-   PrivateInitiatorusingFileDrops.xml  
  
    -   Orquestación: Microsoft.Solutions.BTARN.PrivateInitiator.PrivateInitiatorProcess  
  
    -   Puerto de envío: PrivateInitiator_To_File  
  
    -   Puerto de recepción: File_To_PrivateInitiator  
  
    -   Ubicación de recepción: File_To_PrivateInitiator  
  
-   PrivateResponderusingFileDrops.xml  
  
    -   Orquestación: Microsoft.Solutions.BTARN.PrivateResponder.PrivateResponderProcess  
  
    -   Puerto de envío: PrivateResponder_To_File  
  
    -   Puerto de recepción: File_To_PrivateResponder  
  
    -   Ubicación de recepción: File_To_PrivateResponder  
  
 El siguiente procedimiento describe cómo importar los enlaces de los archivos de enlace mediante el comando BTSTask. Para obtener más información, vea el tema "Comando ImportBindings" en [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] ayuda.  
  
## <a name="procedure"></a>Procedimiento  
  
#### <a name="to-set-up-btarn-by-using-file-drop-folders"></a>Para configurar BTARN mediante el uso de carpetas de entrega de archivos  
  
1.  Abra el Explorador de BizTalk.  
  
2.  Detenga los dos puertos de envío SQL LOB, PrivateInitiator_To_LOB y PrivateResponder_To_LOB.  
  
3.  Deshabilite los dos Lob SQL Receive puertos, LOB_To_PrivateInitiator y LOB_To_PrivateResponder.  
  
4.  Dar de baja Microsoft.Solutions.BTARN.PrivateResponder.PrivateResponderProcess.  
  
5.  Dar de baja Microsoft.Solutions.BTARN.PrivateInitiator.PrivateInitiatatorProcess.  
  
6.  Cree una carpeta \FileDrops en la carpeta BTARN de C:\Program Files\Microsoft BizTalk \<versión > Accelerator for RosettaNet y, a continuación, cree la siguiente estructura de carpetas en \FileDrops:  
  
    -   \PrivateInitiator  
  
         \FromLOB  
  
         \ToLOB  
  
    -   \PrivateResponder  
  
         \FromLOB  
  
         \ToLOB  
  
7.  Ejecute el comando siguiente (suponiendo que BTARN está instalado en la unidad C:):  
  
    ```  
    BTSTask ImportBindings /Source:C:\Program Files\Microsoft BizTalk <version> Accelerator for RosettaNet\SDK\FileTransport\PrivateInitiatorusingFileDrops.xml  
    ```  
  
8.  Ejecute el comando siguiente (suponiendo que BTARN está instalado en la unidad C:):  
  
    ```  
    BTSTask ImportBindings /Source:C:\Program Files\Microsoft BizTalk <version> Accelerator for RosettaNet\SDK\FileTransport\PrivateResponderusingFileDrops.xml  
    ```  
  
9. Iniciar los puertos de envío: PrivateInitiator_To_File y PrivateResponder_To_File.  
  
10. Habilitar los puertos de recepción: LOB_To_PrivateInitiator y LOB_To_PrivateResponder.  
  
## <a name="see-also"></a>Vea también  
 [Ejemplos de mensajería](../../adapters-and-accelerators/accelerator-rosettanet/messaging-samples.md)