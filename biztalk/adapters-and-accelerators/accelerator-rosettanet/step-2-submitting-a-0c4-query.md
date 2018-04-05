---
title: 'Paso 2: Enviar un 0c4 consulta | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- double action tutorial, submitting requests
ms.assetid: ce50b892-c87c-414a-94c5-b40947fec68f
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 88c621b6891b816f72603202bd6f2214882eb4b5
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="step-2-submitting-a-0c4-query"></a>Paso 2: Enviar un 0c consultar 4
En este paso, preparará y enviará una solicitud mediante el proceso de interfaz de socio (PIP) 0C4: consulta sincrónica de prueba. RosettaNet define este PIP para asegurarse de que un canal de comunicación sincrónica funciona correctamente entre dos organizaciones diferentes. Dado que este PIP tiene un patrón de comunicación sincrónica, [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] no envía confirmaciones de recepción. Este PIP sigue el mismo patrón que otros PIP sincrónicos de doble acción, como el PIP 2A9: consulta de información técnica del producto.  
  
### <a name="to-submit-a-0c4---synchronous-test-query"></a>Para enviar un 0C4: consulta sincrónica de prueba  
  
1.  En el equipo de Fabrikam, en Internet Explorer, busque y abra http://localhost/LOBWebApplication/default.aspx.  
  
2.  En la página **Enviar mensaje** , haga lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Organización principal**|Escriba **FABRIKAM**.|  
    |**Organización de socios comerciales**|Escriba **CONTOSO**.|  
    |**Código PIP**|Escriba **0C4**.|  
    |**Versión de PIP**|Escriba **R01.02**.|  
    |**Id. de instancia de PIP**|Escriba **0C4_Test**. **Importante:** para evitar errores de Id. de mensaje duplicado, debe asegurarse de que el **PIP** es único para cada mensaje que envíe. Si ejecuta la prueba 0C4 en el futuro, tendrá que cambiar este campo.|  
    |**Categoría de mensaje**|Escriba **Acción**.|  
  
3.  Con el Bloc de notas u otro editor de texto, abra el archivo 0c4_request.XML situado en la  *\<unidad\>*: \Program BizTalk 2009 Accelerator para la carpeta RosettaNet\SDK\LOBApplication\SampleInstances, y, a continuación, copie y pegue el contenido en el **contenido de servicio** campo LOBWebApplication.  
  
4.  Haga clic en **Enviar** para enviar la consulta 0C4 al equipo de Contoso.  
  
### <a name="to-verify-successful-communication-on-the-fabrikam-computer"></a>Para comprobar que la comunicación es correcta en el equipo de Fabrikam  
  
-   En la página **Estado del mensaje** de LOBWebApplication, compruebe si recibe de dos mensajes entrantes.  
  
    > [!NOTE]
    >  Debería recibir un mensaje de categoría 50, que es el mensaje de respuesta del equipo de Contoso. Un mensaje de categoría -99 indica un error. Puede utilizar el Visor de eventos para determinar cuál es el mensaje de error real.  
  
### <a name="to-verify-successful-communication-on-the-contoso-computer"></a>Para comprobar que la comunicación es correcta en el equipo de Contoso  
  
1.  Haga clic en **Inicio**, seleccione **Todos los programas**, elija **Microsoft SQL Server**y, a continuación, haga clic en **SQL Server Management Studio**.  
  
2.  En el cuadro de diálogo **Conectarse al servidor** , en el cuadro **SQL Server** , escriba **localhost**, seleccione **Autenticación de Windows**y, después, haga clic en **Conectar**.  
  
    > [!NOTE]
    >  Si el Agente SQL Server no está iniciado, haga clic con el botón secundario sobre él y después haga clic en **Iniciar**.  
  
3.  En Microsoft SQL Server Management Studio, haga clic en **Nueva consulta**.  
  
4.  En el \<tabla\> cuadro de texto, seleccione **BTARNDATA** en la lista.  
  
5.  En la ventana de SQL, escriba la siguiente instrucción SQL:  
  
    ```  
    SELECT * From MessagesToLOB  
    ```  
  
6.  Haga clic en **Ejecutar** para ejecutar la instrucción SQL.  
  
7.  En la ventana de consulta, en el panel de resultados, compruebe que ve un mensaje entrante.  
  
    > [!NOTE]
    >  Debería ver un mensaje de categoría 10 que representa la solicitud original enviada por el equipo de Fabrikam.  
  
8.  En la ventana de SQL, escriba la siguiente instrucción SQL:  
  
    ```  
    SELECT * From MessagesFromLOB  
    ```  
  
9. Haga clic en **Ejecutar** para ejecutar la instrucción SQL.  
  
10. En la ventana de consulta, en el panel de resultados, compruebe que ve un mensaje saliente.  
  
    > [!NOTE]
    >  Debería ver un mensaje de categoría 50 que representa la respuesta de Contoso a la consulta PIP 0C4 enviada por Fabrikam. En un escenario de doble acción sincrónico, el equipo de respuesta no envía una confirmación al equipo iniciador en respuesta al mensaje de consulta inicial. El mensaje de respuesta sirve como confirmación.  
  
## <a name="see-also"></a>Vea también  
 [Paso 3: Enviar una solicitud de 3A2](../../adapters-and-accelerators/accelerator-rosettanet/step-3-submitting-a-3a2-request.md)   
 [Flujo de mensajes en BTARN](../../adapters-and-accelerators/accelerator-rosettanet/message-flow-in-btarn.md)