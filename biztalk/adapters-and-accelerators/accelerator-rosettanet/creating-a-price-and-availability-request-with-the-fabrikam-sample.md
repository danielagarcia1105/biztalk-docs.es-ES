---
title: Crear un precio y disponibilidad de solicitud con el ejemplo Fabrikam | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- private process tutorial, creating requests
ms.assetid: 6e4f4589-8f01-4b9e-93ee-c9371f32e04a
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7d0619dc77496fd1547505221ff2f437bf486fb8
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25965922"
---
# <a name="creating-a-price-and-availability-request-with-the-fabrikam-sample"></a>Crear un precio y una solicitud de disponibilidad con el ejemplo de Fabrikam
En este paso, creará una solicitud de precio y disponibilidad 3A2 mediante la herramienta de LOBWebApplication.  
  
### <a name="to-submit-a-3a2-price-and-availability-request-to-contoso"></a>Para enviar una solicitud de precio y disponibilidad 3A2 a Contoso  
  
1.  En el Explorador de Internet, vaya a http://\<*fabrikam_computername*\>/LOBWebApplication/default.aspx.  
  
2.  En el **LOBWebApplication** página, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Organización principal**|Escriba **FABRIKAM**.|  
    |**Organización de socios comerciales**|Escriba **CONTOSO**.|  
    |**Código PIP**|Tipo de **3A2**.|  
    |**Versión PIP**|Tipo de **R02.00.00A**.|  
    |**Categoría de mensaje**|Escriba **Acción**.|  
  
3.  Con el Bloc de notas u otro editor de texto, abra el **3A2_Request.xml** archivo en C:\Program Files\Microsoft BizTalk \<versión\> Acelerador para RosettaNet\SDK\LOBApplication\SampleInstancesfolder Copie y pegue el texto en el **contenido de servicio** campo en la herramienta de LOBWebApplication.  
  
4.  Haga clic en **enviar** para enviar la solicitud de 3A2 a Contoso.  
  
### <a name="to-verify-successful-communication-on-the-fabrikam-computer"></a>Para comprobar que la comunicación es correcta en el equipo de Fabrikam  
  
1.  En la página **Estado del mensaje** de LOBWebApplication, compruebe si recibe de dos mensajes entrantes.  
  
    > [!NOTE]
    >  En primer lugar debe recibir un mensaje de 25 de categoría lo que significa una confirmación de recepción desde el equipo de Contoso. A continuación, debería recibir un mensaje de categoría 50 que es el mensaje de respuesta desde el equipo de Contoso. Un mensaje de categoría -99 indica un error. Puede usar **Visor de eventos** para determinar el mensaje de error real.  
  
2.  Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft SQL Server 2008 R2**y, a continuación, haga clic en **SQL Server Management Studio**.  
  
3.  En el cuadro de diálogo servidor, conectar con en el **SQL Server** , escriba **localhost**, seleccione **autenticación de Windows**y, a continuación, haga clic en **conectar**.  
  
4.  En Microsoft SQL Server Management Studio, haga clic en **Nueva consulta**.  
  
5.  En el  **\<tabla\> texto** cuadro de diálogo, seleccione **BTARNDATA** en la lista.  
  
6.  En el **SQL** ventana, escriba la siguiente instrucción SQL:  
  
    ```  
    SELECT * From MessagesFromLOB  
    ```  
  
7.  Haga clic en **Ejecutar** para ejecutar la instrucción SQL.  
  
8.  En la ventana de consulta, en el panel de resultados, compruebe que puede ver dos mensajes entrantes.  
  
    > [!NOTE]
    >  Debería ver un mensaje de 25 de categoría que representa la confirmación de recepción enviada desde Contoso en el equipo de Fabrikam. También verá un mensaje de categoría 50 que representa la respuesta enviada desde la aplicación de Contoso línea de negocio (LOB) en el equipo de Fabrikam. También puede usar el campo ServiceContent para comprobar la respuesta.  
  
### <a name="to-verify-successful-communication-on-the-contoso-computer"></a>Para comprobar que la comunicación es correcta en el equipo de Contoso  
  
1.  Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft SQL Server 2008 R2**y, a continuación, haga clic en **SQL Server Management Studio**.  
  
2.  En el cuadro de diálogo servidor, conectar con en el **SQL Server** , escriba **localhost**, seleccione **autenticación de Windows**y, a continuación, haga clic en **conectar**.  
  
3.  En Microsoft SQL Server Management Studio, haga clic en **Nueva consulta**.  
  
4.  En el  **\<tabla\> texto** cuadro de diálogo, seleccione **BTARNDATA** en la lista.  
  
5.  En el **SQL** ventana, escriba la siguiente instrucción SQL:  
  
    ```  
    SELECT * From MessagesToLOB  
    ```  
  
6.  Haga clic en **Ejecutar** para ejecutar la instrucción SQL.  
  
7.  En la ventana de consulta, en el panel de resultados, compruebe que puede ver dos mensajes entrantes.  
  
    > [!NOTE]
    >  En primer lugar debe recibir un mensaje de categoría 10 que representa la solicitud original enviada por el equipo de Fabrikam. A continuación, debería recibir un mensaje de 25 de categoría lo que significa el mensaje de confirmación de recepción.  
  
8.  En el **SQL** ventana, escriba la siguiente instrucción SQL:  
  
    ```  
    SELECT * From MessagesFromLOB  
    ```  
  
9. Haga clic en **Ejecutar** para ejecutar la instrucción SQL.  
  
10. En la ventana de consulta, en el panel de resultados, compruebe que ve un mensaje saliente.  
  
    > [!NOTE]
    >  Debería ver un mensaje de 25 de categoría que representa la confirmación de recepción enviada desde Contoso en el equipo de Fabrikam. También verá un mensaje de categoría 50 que representa la respuesta enviada desde la aplicación de Contoso línea de negocio (LOB) en el equipo de Fabrikam.  
  
## <a name="see-also"></a>Vea también  
 [Tutorial de procesos privados](../../adapters-and-accelerators/accelerator-rosettanet/private-process-tutorial.md)