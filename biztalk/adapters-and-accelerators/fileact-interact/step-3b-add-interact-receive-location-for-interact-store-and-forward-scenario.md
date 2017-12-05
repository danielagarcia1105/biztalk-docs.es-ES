---
title: "Paso 3B: agregar un INTERACTÚE ubicación de recepción para el almacén de interacción y el escenario de reenvío | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: da077518-b2ee-4b5f-88d0-fe73af2baa7a
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0e9aa8e153cf510f2d24cbe30a62317d26810e4a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="step-3b-add-an-interact-receive-location-for-the-interact-store-and-forward-scenario"></a>Paso 3B: agregar un INTERACTÚE ubicación de recepción para el almacén de interacción y el escenario de reenvío
Completa [paso 3A: agregar una ubicación de recepción de archivo para el almacén de interacción y reenviar escenario](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-interact-store-and-forward-scenario.md) antes de comenzar este paso.
  
## <a name="add-an-interact-receive-location"></a>Agregar ubicación de recepción de una interacción  
  
1.  Iniciar **administración de BizTalk Server**.  
  
2.  En el árbol de consola, expanda el grupo de BizTalk y, a continuación, expanda la aplicación de BizTalk para el que desea crear un puerto de recepción.  
  
3.  Haga clic en **puertos de recepción**, seleccione **New**y, a continuación, haga clic en **puerto de recepción unidireccional.**  
  
4.  En el **propiedades de puerto de recepción** ventana, nombre el puerto de recepción, Tutorial_IA_HandleRequestOneWay_SnF.  
  
5.  En el **propiedades de puerto de recepción** ventana, en la **ubicaciones de recepción** , haga clic en **nuevo**.  
  
6.  En el **propiedades de la ubicación de recepción** ventana, en la **General** ficha, desde el **tipo de transporte** lista desplegable, seleccione **INTERACT**, y, a continuación, haga clic en **configurar**.  
  
7.  En el **propiedades de transporte interactuar** diálogo cuadro, realice lo siguiente:  
  
    |**Use esto**|**Para ello**|  
    |------------------|--------------------|  
    |**Contraseña**|Escriba la contraseña que usa para conectarse a SAG. Para obtener más información, consulte la Ayuda de SAG.|  
    |**Nombre de usuario.**|Escriba el nombre de usuario que utiliza para conectarse a SAG.|  
    |**Nombre de la aplicación**|Escriba la dirección del servidor \<nombre de la interfaz de aplicación\> para el SAG cuadro enrutamiento conjunto.|  
    |**Modo de cifrado**|En la lista desplegable, seleccione **avanzadas**.|  
    |**LogMessageBody**|En la lista desplegable, seleccione **FALSE**. **Nota:** si se establece en TRUE, conserva el cuerpo del mensaje en la base de datos de seguimiento de BizTalk. Sin embargo, por motivos de seguridad, el cuerpo del mensaje nunca se ve en el portal de BAM.|  
    |**LogMessages**|En la lista desplegable, seleccione **TRUE**. Esto permite que los eventos de mensaje capturar y realizar el seguimiento en el portal de BAM.|  
    |**Formato de mensaje**|En la lista desplegable, seleccione **InterActMessage**.|  
    |**MemberRef**|En la lista desplegable, seleccione **ResponseHeader**.|  
    |**Indicador de sin repudio**|En la lista desplegable, seleccione **FALSE**.|  
    |**Servicio de respuesta**|Escriba la correspondiente \<Respondedor\> cadena, según su aprovisionamiento con SWIFT.|  
    |**ResponseCrypto**|En la lista desplegable, seleccione **FALSE**.|  
    |**Timeout**|Escriba un número adecuado de segundos antes de que se realizarán el tiempo de espera.|  
    |**Adquirir cola**|Escriba el nombre de cola, en función de su aprovisionamiento con SWIFT.|  
    |**ForceAcquire**|En la lista desplegable, seleccione **TRUE**.|  
    |**Ordenar por**|En la lista desplegable, seleccione **Interact**.|  
    |**Sesión de inserción**|En la lista desplegable, seleccione **TRUE**.|  
    |**Modo de recuperación**|En la lista desplegable, seleccione **TRUE**.|  
    |**Extremo SNL**|Escriba el extremo adecuado para el conjunto de enrutamiento SAG. Este valor debe coincidir con el punto de conexión de SnL que configuró en SAG.|  
  
8.  Haga clic en **Aceptar**.  
  
9. En el **propiedades de la ubicación de recepción** ventana, en la **General** ficha, realice lo siguiente:  
  
    |**Use esto**|**Para ello**|  
    |------------------|--------------------|  
    |**Controlador de recepción**|En la lista desplegable, seleccione **BizTalkServerIsolatedHost**.|  
    |**La canalización de recepción**|En la lista desplegable, seleccione **XMLReceive**.|  
  
10. Haga clic en **Aceptar**.  
  
## <a name="complete-steps"></a>Complete los pasos
 [Paso 3: Crear puertos de envío y puertos de recepción para el almacén de interacción y el escenario de reenvío](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-interact-store-and-forward-scenario.md)   
 [Paso 3A: agregar un archivo de ubicación de recepción para el almacén de interacción y el escenario de reenvío](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-interact-store-and-forward-scenario.md)   
 [Paso 3C: Agregar un puerto de envío de ARCHIVOS para capturar el mensaje Sw:HandleRequest para el escenario de almacenamiento y reenvío de InterAct](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-interact-store-and-forward.md)  
 [Paso 3D: Agregar un puerto de envío INTERACT para el escenario de almacenamiento y reenvío de InterAct](../../adapters-and-accelerators/fileact-interact/step-3d-add-an-interact-send-port-for-the-interact-store-and-forward-scenario.md)