---
title: 'Paso 4: Enviar una solicitud de 3A4 | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: double action tutorial, submitting requests
ms.assetid: 2d812cbc-51bc-48d5-b0b2-3698d33664ec
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ff36b6181b167d70340a65913e1e85e7acfeeaf4
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="step-4-submitting-a-3a4-request"></a>Paso 4: Enviar una solicitud de 3A4
En este paso, se preparará y enviará una solicitud con el proceso de interfaz de socio (PIP) para un 3A4 - pedido de compra de la solicitud. Este PIP permite a una organización de comprador enviar una solicitud de pedido de compra a un proveedor. Por lo general, se solicita la 3A4 - pedido de compra de solicitud después de ejecutar una consulta de la disponibilidad de producto mediante el 3A2 - solicitud precio y disponibilidad PIP. El PIP 3A4 es una PIP asincrónica que envía confirmaciones de recepción.  
  
 ![&#60; No hay ningún cambio &#62; ] (../../adapters-and-accelerators/accelerator-rosettanet/media/rn3-intro-eetut-3a4flow.gif "RN3_Intro_EETut_3A4Flow")  
  
### <a name="to-submit-a-3a4---request-purchase-order"></a>Para enviar un 3A4 - solicitud de pedido de compra  
  
1.  En el equipo de Fabrikam, en Internet Explorer, busque y abra http://localhost/LOBWebApplication/default.aspx.  
  
2.  En la página **Enviar mensaje** , haga lo siguiente:  
  
    |**Use esto**|**Para ello**|  
    |------------------|--------------------|  
    |**Organización principal**|Escriba **FABRIKAM**.|  
    |**Organización de socios comerciales**|Tipo de **Contoso**.|  
    |**Código PIP**|Tipo de **3A4**.|  
    |**Versión de PIP**|Tipo de **V02.02.00**.|  
    |**Id. de instancia de PIP**|Tipo de **3A4_Test**. **Importante:** para evitar errores de Id. de mensaje duplicado, debe asegurarse de que el **Id. de instancia de Pip** es único para cada mensaje que envíe. Si ejecuta la prueba de 3A4 en el futuro, tendrá que cambiar este campo.|  
    |**Categoría de mensaje**|Escriba **Acción**.|  
  
3.  Con el Bloc de notas u otro editor de texto, abra el archivo 3A4_Request.xml en el \< *unidad*\>: \Program BizTalk \<versión\> Acelerador para RosettaNet\SDK\ Carpeta LOBApplication\SampleInstances y, a continuación, copie y pegue el contenido en el **contenido de servicio** campo LOBWebApplication.  
  
4.  Haga clic en **enviar** para enviar la solicitud 3A4 en el equipo de Contoso.  
  
### <a name="to-verify-successful-communication-on-the-fabrikam-computer"></a>Para comprobar que la comunicación es correcta en el equipo de Fabrikam  
  
-   En la página **Estado del mensaje** de LOBWebApplication, compruebe si recibe de dos mensajes entrantes.  
  
    > [!NOTE]
    >  En primer lugar debe recibir un mensaje de 25 de categoría lo que significa una confirmación de recepción desde el equipo de Contoso. A continuación, debería recibir un mensaje de categoría 50 que es el mensaje de respuesta desde el equipo de Contoso. Un mensaje de categoría -99 indica un error. Puede usar **Visor de eventos** para determinar el mensaje de error real.  
  
### <a name="to-verify-successful-communication-on-the-contoso-computer"></a>Para comprobar que la comunicación es correcta en el equipo de Contoso  
  
1.  Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft SQL Server 2008 R2**y, a continuación, haga clic en **SQL Server Management Studio**.  
  
2.  En el cuadro de diálogo **Conectarse al servidor** , en el cuadro **SQL Server** , escriba **localhost**, seleccione **Autenticación de Windows**y, después, haga clic en **Conectar**.  
  
3.  En Microsoft SQL Server Management Studio, haga clic en **Nueva consulta**.  
  
4.  En el \<tabla\> el cuadro de diálogo de texto, seleccione **BTARNDATA** en la lista.  
  
5.  En la ventana de SQL, escriba la siguiente instrucción SQL:  
  
    ```  
    SELECT * From MessagesToLOB  
    ```  
  
6.  Haga clic en **Ejecutar** para ejecutar la instrucción SQL.  
  
7.  En la ventana de consulta, en el panel de resultados, compruebe que puede ver dos mensajes entrantes.  
  
    > [!NOTE]
    >  En primer lugar debe recibir un mensaje de categoría 10 que representa la solicitud original enviada por el equipo de Fabrikam. A continuación, debería recibir un mensaje de 25 de categoría lo que significa el mensaje de confirmación de acknowledegment.  
  
8.  En la ventana de SQL, escriba la siguiente instrucción SQL:  
  
    ```  
    SELECT * From MessagesFromLOB  
    ```  
  
9. Haga clic en **Ejecutar** para ejecutar la instrucción SQL.  
  
10. En la ventana de consulta, en la **resultados** panel, compruebe que ve un mensaje saliente.  
  
    > [!NOTE]
    >  Debería ver un mensaje de 25 de categoría que representa la confirmación de recepción enviada desde Contoso en el equipo de Fabrikam. También verá un mensaje de categoría 50 que representa la respuesta enviada desde la aplicación de Contoso línea de negocio (LOB) en el equipo de Fabrikam.  
  
## <a name="see-also"></a>Vea también  
 [Tutorial de doble acción](../../adapters-and-accelerators/accelerator-rosettanet/double-action-tutorial.md)   
 [Flujo de mensajes en BTARN](../../adapters-and-accelerators/accelerator-rosettanet/message-flow-in-btarn.md)