---
title: 'Paso 1: Preparar el Tutorial de AS2 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3421c33b-0ccd-4e9d-b1c3-b161278e4d98
caps.latest.revision: 39
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 75c6be6fb76debac7f5a143fa1616a999dee326c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279548"
---
# <a name="step-1-prepare-for-the-as2-tutorial"></a>Paso 1: Preparar el Tutorial de AS2
![Paso 1 de 11](../core/media/tut-step1-of-11.gif "Tut_Step1_of_11")  
  
 El tutorial de AS2 se ejecuta en un único equipo. Para preparar el tutorial, debe instalar y configurar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] tal y como se describe en [Introducción a la instalación de BizTalk Server 2013 y 2013 R2](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5) sección. También debe agregar una referencia a la aplicación EDI de BizTalk Server como se describe en este tema. Los archivos necesarios para el tutorial de AS2 se encuentran en la carpeta [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial.  
  
> [!NOTE]
>  Para que este tutorial funcione, debe usar la misma cuenta de inicio de sesión tanto para la instancia de host en curso como para la instancia de host aislado.  
  
> [!NOTE]
>  Para que funcione este tutorial, el host de BizTalk Server que se usó para este tutorial debe estar marcado como de 32 bits.  
  
> [!NOTE]
>  Para que funcione este tutorial, debe ejecutarse en una plataforma que use IIS 7.0 o IIS 7.5 y la configuración de aplicación de 32 bits para el grupo de aplicaciones debe estar establecida en verdadera.  
  
 Las carpetas del tutorial de AS2 incluyen tres carpetas en las que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] escribirá archivos de salida de prueba (carga EDI, 997 y MDN). Estas carpetas ya están creadas, pero debe establecer los permisos de seguridad para dos de las carpetas de 997 y MDN (vea el siguiente procedimiento).  
  
 Las carpetas y archivos necesarios para el tutorial son los siguientes:  
  
|Carpeta\Archivo|Finalidad|  
|------------------|-------------|  
|\\_997ToFabrikam|Esta carpeta vacía recibirá el mensaje de confirmación 997 devuelto después del procesamiento EDI. La carpeta simula la aplicación que origina el mensaje EDI en la entidad Fabrikam.|  
|\\_EDIXMLToContoso|Esta carpeta vacía recibirá el archivo de carga XML una vez BizTalk Server procesa el mensaje EDI. Esta carpeta simula la aplicación para línea empresarial, que es el destino final de la carga EDI.|  
|\\_MDNToFabrikam|Esta carpeta vacía recibirá el mensaje MDN devuelto de BizTalk Server después del procesamiento de AS2. La carpeta simula una aplicación en la entidad Fabrikam.|  
|\Fabrikam|Esta carpeta contiene el archivo Default.aspx que almacena el 997 en la carpeta _997ToFabrikam y guarda el MDN en la carpeta _MDNToFabrikam.|  
|\Schemas|Esta carpeta contiene el esquema X12_00401_864.xsd y otros esquemas que usa BizTalk para procesar el mensaje EDI. La carpeta también contiene el proyecto Schemas.btproj que generará e implementará para implementar los esquemas.|  
|\Sender|Esta carpeta contiene el proyecto Sender.csproj que generará y compilará para crear Sender.exe, que se usa para enviar el mensaje de prueba X12_00401_864.edi (en la carpeta \AS2 Tutorial) y para devolver el MDN.|  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe iniciar sesión como miembro del grupo Administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
## <a name="procedures"></a>Procedimientos  
  
#### <a name="to-set-the-security-permission-for-the-997-and-mdn-folders"></a>Para establecer el permiso de seguridad para las carpetas 997 y MDN  
  
1.  En el Explorador de Windows, desplácese a la [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\\carpeta _997ToFabrikam. Haga clic en el \\_997ToFabrikam carpeta y, a continuación, haga clic en **propiedades**.  
  
2.  Haga clic en el **seguridad** ficha y, a continuación, haga clic en **editar**. En el **permisos** cuadro de diálogo, haga clic en **agregar**.  
  
3.  En el **Seleccionar usuarios, equipos, cuentas de servicio o grupos** cuadro de diálogo, en el panel de nombres de objeto, escriba `Everyone`y, a continuación, haga clic en **Aceptar**.  
  
4.  Seleccione **todos** en el **nombres de grupo o usuario** cuadro, haga clic en la casilla de verificación para **escribir** (bajo la **permitir** columna) en el **Permisos** panel y, a continuación, haga clic en **Aceptar**.  
  
5.  Haga clic en **Aceptar**.  
  
6.  Repita estos pasos para el \\carpeta _MDNToFabrikam.  
  
#### <a name="to-mark-the-biztalk-server-host-as-32-bit"></a>Procedimiento para marcar a BizTalk Server Host como de 32 bits  
  
1.  > [!NOTE]
    >  solo se pueden usar las canalizaciones de AS2 en procesos de 32 bits. Si [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] está instalado en un sistema operativo de 64 bits, deben realizarse los siguientes pasos para marcar los procesos de host como solo de 32 bits.  
  
     Seleccione **iniciar**, seleccione **todos los programas**, seleccione **Microsoft BizTalk Server**y, a continuación, seleccione **administración de BizTalk Server**.  
  
2.  En el árbol de consola, expanda **administración de BizTalk Server**, expanda el grupo de BizTalk, seleccione **configuración de plataforma**y, a continuación, seleccione **Hosts**.  
  
3.  En el panel de detalles, haga clic en el host in-process que desea usar para este tutorial y, a continuación, seleccione **propiedades**.  
  
4.  En el **propiedades de Host** cuadro de diálogo, en la **General** ficha, seleccione **sólo de 32 bits**y, a continuación, haga clic en **Aceptar**.  
  
5.  Repita los pasos 3 a 4 para el host aislado.  
  
 Si BizTalk Server está instalado en un sistema operativo de 64 bits, también de be configurar IIS para que se ejecute en modo de 32 bits al usar un proceso de host de BizTalk de 32 bits. Se presentan las instrucciones para configurar IIS en [paso 5: configurar las páginas Web de socios comerciales](../core/step-5-configure-the-trading-partner-web-pages.md), como IIS le permite establecer el proceso de trabajo de 32 bits en un grupo cada aplicación.  
  
#### <a name="to-add-reference-to-the-biztalk-edi-application"></a>Procedimiento para agregar una referencia a la aplicación EDI de BizTalk  
  
1.  En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, en la **aplicaciones** nodo, haga clic en la aplicación que desea usar con EDI, como BizTalk Application 1. Seleccione **agregar**y, a continuación, haga clic en referencias.  
  
2.  En el **Agregar referencia de aplicación** cuadro de diálogo, seleccione **aplicación EDI de BizTalk**y, a continuación, haga clic en **Aceptar**.  
  
## <a name="next-steps"></a>Pasos siguientes  
 Implementar el esquema de ejemplo X12 tal y como se describe en [paso 2: crear e implementar el ejemplo X12 esquema](../core/step-2-create-and-deploy-the-sample-x12-schema.md)  
  
## <a name="see-also"></a>Vea también  
 [Tutorial 3: Tutorial de AS2](../core/tutorial-3-as2-tutorial.md)