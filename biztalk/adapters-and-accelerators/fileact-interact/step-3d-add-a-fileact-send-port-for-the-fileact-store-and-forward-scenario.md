---
title: 'Paso 3D: agregar un puerto de envío de FILEACT para el escenario de reenvío y almacenamiento de FileAct | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7366140b-ab89-4bea-9cdb-aa27e8dea8a0
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a3944c58aecda3d9ea984e0ef0ce9a2bf168ea80
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25965490"
---
# <a name="step-3d-add-a-fileact-send-port-for-the-fileact-store-and-forward-scenario"></a>Paso 3D: agregar un puerto de envío de FILEACT para el escenario de reenvío y almacenamiento de FileAct
Antes de comenzar este paso, debe completar [paso 3c: agregar un puerto de envío de archivo para capturar la Sw:HandleFileRequest y Sw:HandleSnFRequest mensajes para el escenario de al día y el almacenamiento de FileAct](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlefilerequest-and-sw-handlesnfrequest.md).  
  
### <a name="to-add-a-fileact-send-port"></a>Para agregar un puerto de envío FILEACT  
  
1.  Iniciar **administración de BizTalk Server**.  
  
2.  En el árbol de consola, expanda el grupo de BizTalk y, a continuación, expanda la aplicación de BizTalk para el que desea crear un puerto de envío.  
  
3.  Haga clic en **puertos de envío**, seleccione **New**y, a continuación, haga clic en **puerto de envío de petición-respuesta estático**.  
  
4.  En el **propiedades de puerto de envío** ventana, nombre el puerto de envío Tutorial_FA_SendRequest_SnF.  
  
5.  En el **propiedades de puerto de envío** ventana, desde el **tipo de transporte** lista desplegable, seleccione **FILEACT**y, a continuación, haga clic en **configurar**.  
  
6.  En el **propiedades de transporte FILEACT** diálogo cuadro, realice lo siguiente:  
  
    |**Use esto**|**Para ello**|  
    |------------------|--------------------|  
    |**Contraseña**|Establecer la contraseña según corresponda para la conectividad SAG.|  
    |**Nombre de usuario.**|Defina el nombre de usuario según corresponda para la conectividad SAG.|  
    |**Modo del adaptador**|En la lista desplegable, seleccione **almacenar y retransmitir**.|  
    |**Indicador de sin repudio**|En la lista desplegable, seleccione **FALSE**.|  
    |**Tipo de solicitud**|Establecer correspondientes \<RequestType\> cadena, según su aprovisionamiento con SWIFT.|  
    |**ResponseCrypto**|En la lista desplegable, seleccione **FALSE**.|  
    |**Solicitante**|Establecer correspondientes \<solicitante\> cadena, según su aprovisionamiento con SWIFT.|  
    |**Servicio de respuesta**|Establecer correspondientes \<Respondedor\> cadena.|  
    |**Nombre del servicio**|Establecer correspondientes \<nombre del servicio\>.|  
    |**Indicador de confirmación**|En la lista desplegable, seleccione **FALSE**.|  
    |**FileCompression**|En la lista desplegable, seleccione **ninguno**.|  
    |**Extremo de eventos**|Escriba el extremo SAG adecuado.|  
    |**Nombre de la carpeta física**|Escriba C:\SWIFTAdapterTutorial\Fileact\ClientLocation.|  
    |**Transferencia de extremo**|Escriba el extremo adecuado para el conjunto de enrutamiento SAG. Este valor debe coincidir con el punto de conexión de SnL que configuró en SAG.|  
    |**PerfilServicio**|En la lista desplegable, seleccione **recuento de transacciones**.|  
    |**Notificación de entrega**|En la lista desplegable, seleccione **FALSE**.|  
    |**Cola de notificación**|Escriba el nombre de cola, en función de su aprovisionamiento con SWIFT.|  
  
    > [!WARNING]
    >  Si el mensaje con el recuento de transacciones que se va a transferirse, establezca el modo de perfil de servicio para "recuento de transacciones" en el FileAct puerto de envío.  
  
7.  Haga clic en **Aceptar**.  
  
8.  En el **propiedades de puerto de envío** ventana, haga lo siguiente:  
  
    |**Use esto**|**Para ello**|  
    |------------------|--------------------|  
    |**Controlador de envío**|En la lista desplegable, seleccione el host de Fileact.|  
    |**Canalización de envío**|En la lista desplegable, seleccione **XMLTransmit**.|  
    |**La canalización de recepción**|En la lista desplegable, seleccione **XMLReceive**.|  
  
9. En el **propiedades de puerto de envío** ventana, en la **filtros** ficha, realice lo siguiente:  
  
    |**Use esto**|**Para ello**|  
    |------------------|--------------------|  
    |**Propiedad**|En la lista desplegable, seleccione **BTS. ReceivePortName**.|  
    |**Operador**|En la lista desplegable, seleccione  **==** .|  
    |**Valor**|Tutorial_FA_InputRequest_SnF de tipo.|  
    |**Agrupar por**|Dejar el valor predeterminado.|  
  
10. Haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
 [Paso 3: Crear puertos de envío y puertos de recepción para el escenario de reenvío y almacenamiento de FileAct](../../adapters-and-accelerators/fileact-interact/step-3-create-send-ports-and-receive-ports-for-the-fileact-store-and-forward.md)   
 [Paso 3A: agregar un archivo de ubicación de recepción para el escenario de reenvío y almacenamiento de FileAct](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-fileact-store-and-forward-scenario.md)   
 [Paso 3B: agregar un FILEACT ubicación de recepción para el escenario de reenvío y almacenamiento de FileAct](../../adapters-and-accelerators/fileact-interact/step-3b-add-a-fileact-receive-location-for-fileact-store-and-forward-scenario.md)   
 [Paso 3C: Agregar un puerto de envío de ARCHIVOS para capturar los mensajes Sw:HandleFileRequest y Sw:HandleSnFRequest para el escenario de almacenamiento y reenvío de FileAct](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlefilerequest-and-sw-handlesnfrequest.md)