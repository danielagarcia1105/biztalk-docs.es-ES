---
title: Soporte extendido de codificación | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 93a40fa6-d0da-416e-97fb-675ddde3f005
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f12412e42eda63400260c466bf4c9b34f93881db
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989325"
---
# <a name="extended-encoding-support"></a>Soporte extendido de codificación
De forma predeterminada, se recibe el HL7 canalización, BTAHL72X, solo admite la codificación ASCII. Esto significa que los caracteres de un mensaje de entrada con un valor equivalente mayor que 127 se reemplazan por "?". Esto es porque no se representan caracteres con un valor equivalente mayor que 127 en el juego de caracteres ASCII.  
  
 [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] proporciona compatibilidad para dos codificaciones nueva:  
  
- Europeo occidental  
  
- UTF-8  
  
  Crear y generar un componente de canalización personalizado para implementar el soporte extendido de codificación. El componente de canalización personalizada utiliza el BTAHL7 2.X Desensamblador. Crear una ubicación de recepción que usa la canalización personalizada para procesar los mensajes. Para probar la ubicación de recepción y una canalización personalizada, cree un puerto de envío que usa el 2.XSendPipeline BTAHL7.  
  
### <a name="to-create-a-custom-pipeline"></a>Para crear una canalización personalizada  
  
1. En [!INCLUDE[btsVStudio2008](../../includes/btsvstudio2008-md.md)], agregue un nuevo **proyecto vacío de servidor BizTalk**.  
  
2. En el Explorador de soluciones, haga clic en el nuevo proyecto, haga clic en **agregar**y, a continuación, haga clic en **nuevo elemento**.  
  
3. En el **Agregar nuevo elemento** diálogo cuadro, agregue un nuevo **canalización de recepción**.  
  
4. En el cuadro de herramientas de canalización, arrastre el **BTAHL7 2.X Desensamblador** al editor de canalización y colóquela en la **desensamblar** fase **Coloque aquí** destino.  
  
   > [!NOTE]
   >  Si el Desensamblador de 2.7 BTAHL7 no está en el cuadro de herramientas, haga clic en el cuadro de herramientas y haga clic en **elegir elementos**. En el **elegir elementos del cuadro de herramientas** cuadro de diálogo el **componente de canalización de BizTalk** ficha, seleccione el **BTAHL7 2.X Desensamblador** casilla de verificación y, a continuación, haga clic en **Aceptar** .  
  
5. En el panel de propiedades para el **BTAHL7 2.X Desensamblador**, desde el **juego de caracteres de codificación** lista desplegable, seleccione **Europeo occidental** o **UTF8**codificación.  
  
   > [!NOTE]
   >  HL7 solo es compatible con ASCII (valor predeterminado), Europa occidental y la codificación UTF8. No seleccione las opciones de codificación porque no es compatible con HL7.  
  
6. En el menú **Archivo** , haga clic en **Guardar todo**.  
  
7. Implemente el proyecto.  
  
    Cree una nueva ubicación de recepción para continuar.  
  
### <a name="to-create-a-receive-location-that-uses-the-custom-pipeline"></a>Para crear una ubicación de recepción que usa la canalización personalizada  
  
1. En el **iniciar** menú, haga clic en **programas**, apunte a [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2. En la consola de administración de BizTalk Server, expanda [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)] **administración**, expanda **grupo de BizTalk**, expanda **aplicaciones**, expanda la aplicación que haya designado para el ensamblado de canalización (de forma predeterminada, **BizTalk Application 1**), haga clic en **ubicaciones de recepción**, apunte a **New**y, a continuación, haga clic en **Unidireccional ubicación de recepción**.  
  
3. En el **propiedades de ubicación de recepción** cuadro de diálogo el **canalización de recepción** menú desplegable, seleccione el nombre de la opción de instalación de canalización que ha creado. (Esto es el nombre del objeto de canalización personalizado, no el BTAHL7 canalización 2 X.)  
  
### <a name="to-create-a-send-port-to-test-the-receive-location-and-pipeline"></a>Para crear un puerto de envío para probar la canalización y la ubicación de recepción  
  
1. En el **iniciar** menú, haga clic en **programas**, apunte a [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2. En la consola de administración de BizTalk Server, expanda [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)] **administración**, expanda **grupo de BizTalk**, expanda **aplicaciones**, expanda la aplicación que haya designado para el ensamblado de canalización (de forma predeterminada, **BizTalk Application 1**), haga clic en **puertos de envío**, apunte a **New**y, a continuación, haga clic en **Puerto de envío unidireccional estático**.  
  
3. En el **propiedades de puerto de envío** cuadro de diálogo el **canalización de envío** lista desplegable, seleccione **BTAHL72XSendPipeline**.  
  
### <a name="to-test-the-receive-location-and-pipeline"></a>Para probar la ubicación de recepción y una canalización  
  
-   Coloque un archivo que contiene caracteres especiales y guardarlo con la misma codificación que especificó en la canalización personalizada en la ubicación designada en la ubicación de recepción. El archivo en la ubicación de salida debe conservar los caracteres especiales.  
  
    > [!NOTE]
    >  Si intenta procesar un archivo que utiliza una codificación no compatible (Recuerde que se admiten solo ASCII, Europa occidental y UTF8), se registra un error en el Visor de eventos de aplicación con el Id. de error: 5633.  
  
    > [!NOTE]
    >  Si va a probar una canalización personalizada configurada para la codificación UTF8, debe asociar los caracteres de marca de orden de bytes (BOM) al mensaje que se pasa. Si va a probar una canalización personalizada configurada para la codificación de Europa occidental, no la adjunte caracteres de la lista de materiales.