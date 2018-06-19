---
title: 'Paso 3: Enviar una solicitud de 3A2 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- double action tutorial, submitting requests
ms.assetid: 09f22be8-6d7d-48bf-862b-73248bae0506
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 312e5980636d211f1e023331826e016eb141eb4b
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25967538"
---
# <a name="step-3-submitting-a-3a2-request"></a>Paso 3: Enviar una solicitud de 3A2
En este paso, se preparará y enviará una solicitud con el proceso de interfaz de socio (PIP) para un 3A2 - solicitud precio y disponibilidad. Este PIP permite a una organización de comprador obtener información sobre un determinado producto, como el precio y el número de unidades disponibles. El comprador, a continuación, puede procesar esta información a través de las reglas de negocios para determinar si se debe adquirir el producto del proveedor.  
  
### <a name="to-submit-a-3a2---request-price-and-availability"></a>Para enviar un 3A2 - solicitud de precio y disponibilidad  
  
1.  En el equipo de Fabrikam, en Internet Explorer, busque y abra http://localhost/LOBWebApplication/default.aspx.  
  
2.  En la página **Enviar mensaje** , haga lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Organización principal**|Escriba **FABRIKAM**.|  
    |**Organización de socios comerciales**|Tipo de **Contoso**.|  
    |**Código PIP**|Tipo de **3A2**. **Importante:** para evitar errores de Id. de mensaje duplicado, debe asegurarse de que el **Pip** es único para cada mensaje que envíe. Si ejecuta la prueba de 3A2 en el futuro, tendrá que cambiar este campo.|  
    |**Versión de PIP**|Tipo de **R02.00.00A**.|  
    |**Id. de instancia de PIP**|Tipo de **3A2_Test**.|  
    |**Categoría de mensaje**|Escriba **Acción**.|  
  
3.  Con el Bloc de notas u otro editor de texto, abra el 3A2_Request.xml de archivo en el  *\<unidad\>*: \ Programa de programa\Microsoft BizTalk \<versión\> Accelerator for RosettaNet\SDK\LOBApplication\SampleInstances carpeta y, a continuación, copie y pegue el contenido en el **contenido de servicio** campo LOBWebApplication.  
  
4.  Haga clic en **enviar** para enviar la solicitud de 3A2 al equipo de Contoso.  
  
### <a name="to-verify-successful-communication-on-the-fabrikam-computer"></a>Para comprobar que la comunicación es correcta en el equipo de Fabrikam  
  
-   En la página **Estado del mensaje** de LOBWebApplication, compruebe si recibe de dos mensajes entrantes.  
  
    > [!NOTE]
    >  En primer lugar debe recibir un mensaje de 25 de categoría lo que significa una confirmación de recepción desde el equipo de Contoso. A continuación, debería recibir un mensaje de categoría 50 que es el mensaje de respuesta desde el equipo de Contoso. Un mensaje de categoría -99 indica un error. Puede usar **Visor de eventos** para determinar el mensaje de error real.  
  
### <a name="to-verify-successful-communication-on-the-contoso-computer"></a>Para comprobar que la comunicación es correcta en el equipo de Contoso  
  
1.  Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft SQL Server 2008 R2**y, a continuación, haga clic en **SQL Server Management Studio**.  
  
2.  En el cuadro de diálogo **Conectarse al servidor** , en el cuadro **SQL Server** , escriba **localhost**, seleccione **Autenticación de Windows**y, después, haga clic en **Conectar**.  
  
3.  En Microsoft SQL Server Management Studio, haga clic en **Nueva consulta**.  
  
4.  En el \<tabla\> cuadro de texto, seleccione **BTARNDATA** en la lista.  
  
5.  En la ventana de SQL, escriba la siguiente instrucción SQL:  
  
    ```  
    SELECT * From MessagesToLOB  
    ```  
  
6.  Haga clic en **Ejecutar** para ejecutar la instrucción SQL.  
  
7.  En la ventana de consulta, en el panel de resultados, compruebe que puede ver dos mensajes entrantes.  
  
    > [!NOTE]
    >  En primer lugar debe recibir un mensaje de categoría 10 que representa la solicitud original enviada por el equipo de Fabrikam. A continuación, debería recibir un mensaje de 25 de categoría lo que significa el mensaje de confirmación de recepción.  
  
8.  En la ventana de SQL, escriba la siguiente instrucción SQL:  
  
    ```  
    SELECT * From MessagesFromLOB  
    ```  
  
9. Haga clic en **Ejecutar** para ejecutar la instrucción SQL.  
  
10. En la ventana de consulta, en el panel de resultados, compruebe que ve un mensaje saliente.  
  
    > [!NOTE]
    >  Debería ver un mensaje de 25 de categoría que representa la confirmación de recepción enviada desde Contoso en el equipo de Fabrikam. También verá un mensaje de categoría 50 que representa la respuesta enviada desde la aplicación de Contoso línea de negocio (LOB) en el equipo de Fabrikam.  
  
## <a name="see-also"></a>Vea también  
 [Paso 4: Enviar una solicitud de 3A4](../../adapters-and-accelerators/accelerator-rosettanet/step-4-submitting-a-3a4-request.md)   
 [Flujo de mensajes en BTARN](../../adapters-and-accelerators/accelerator-rosettanet/message-flow-in-btarn.md)