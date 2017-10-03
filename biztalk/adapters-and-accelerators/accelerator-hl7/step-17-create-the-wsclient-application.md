---
title: "Paso 17: Crear la aplicación WSClient | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WSClient application
- message enrichment tutorial, WSClient application
- creating, WSClient application
ms.assetid: 2849cd4c-30d0-47ab-8161-fab379d5a548
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8028688f918854d8251f7b059c76642800961088
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-17-create-the-wsclient-application"></a>Paso 17: Crear la aplicación WSClient
WSClient.exe (cliente de servicios Web) es una aplicación de consola escrita en [!INCLUDE[btsVCSharp](../../includes/btsvcsharp-md.md)] que muestra cómo enviar datos a la orquestación que se publicó como un servicio Web en los pasos anteriores. La aplicación WSClient acepta cuatro parámetros en orden de entrada: nombre del paciente primero, segundo nombre, apellido y número del seguro social, respectivamente. Para enviar la información del paciente a su servicio Web, use la siguiente sintaxis de línea de comandos:  
  
```  
wsclient john henry smith 123456789  
```  
  
### <a name="to-create-the-wsclient-application"></a>Para crear la aplicación WSClient  
  
1.  En el Explorador de soluciones, haga clic en **solución 'BTAHL7V22Common'**, haga clic en **agregar**y, a continuación, haga clic en **nuevo proyecto**.  
  
2.  En el **Agregar nuevo proyecto** cuadro de diálogo, en la **tipos de proyecto** panel, haga clic en **Visual C#** y en el **plantillas** panel, haga clic en **Aplicación de consola**.  
  
3.  En el **nombre** , escriba **WSClient**. En el **ubicación** campo, vaya a  **\<* unidad*>: \Tutorial** y, a continuación, haga clic en **Aceptar**. El Explorador de soluciones agrega WSClient al árbol y aparece el archivo Program.cs.  
  
4.  En el Explorador de soluciones, haga clic en **WSClient**y, a continuación, haga clic en **Agregar referencia Web**.  
  
5.  En el cuadro de diálogo Agregar referencia Web, haga clic en **Web services en el equipo local**. El equipo local busca servicios Web disponibles y, a continuación, muestra en una lista.  
  
6.  En la lista de servicios Web en el equipo Local, haga clic en **BTAHL7_Project_Doorbell_Orchestration_SOAPReceivePort**, haga clic en **Operation_1**y, a continuación, haga clic en **Agregar referencia**.  
  
7.  Haga doble clic en Program.cs.  
  
8.  Copie el código siguiente y, a continuación, péguelo en la ventana de Program.cs:  
  
    ```  
    using System;  
  
    namespace WSClient  
    {  
       class Class1  
       {  
          [STAThread]  
          static void Main(string[] args)  
          {  
             try   
             {  
                localhost.DoorbellRoot req=new WSClient.localhost.DoorbellRoot();  
                req.FirstName=args[0];  
                req.MiddleName=args[1];  
                req.LastName=args[2];  
                req.SSN=args[3];  
                localhost.BTAHL7_Project_Doorbell_Orchestration_SOAPReceivePort sp=new WSClient.localhost.BTAHL7_Project_Doorbell_Orchestration_SOAPReceivePort();  
                sp.Operation_1(req);  
             }  
             catch (Exception ex)  
             {  
                Console.WriteLine(ex.Message);  
             }  
          }  
       }  
    }  
    ```  
  
9. En el Explorador de soluciones, haga clic en **WSClient**y, a continuación, haga clic en **generar**. Asegúrese de que aparece un mensaje de confirmación en la ventana de salida. Si no aparece ningún mensaje de correcto, solucione **WSClient**. [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]coloca una copia del archivo ejecutable, WSClient.exe, en la \< *unidad*>: \Tutorial\WSClient\bin\Debug carpeta.  
  
 Continúe con [paso 18: probar la nueva solución de enriquecimiento de mensaje](../../adapters-and-accelerators/accelerator-hl7/step-18-test-your-new-message-enrichment-solution.md).  
  
## <a name="see-also"></a>Vea también  
 [Tutorial de enriquecimiento de mensajes](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)