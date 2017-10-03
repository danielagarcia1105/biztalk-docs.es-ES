---
title: Uso del sistema JD Edwards OneWorld | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5346aa04-ebd7-4545-9062-b349fd73b7f1
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 835432e50bce3f347e6f769fb8182ab35fc4f949
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="using-a-jd-edwards-oneworld-system"></a>Uso del sistema JD Edwards OneWorld
El adaptador de JD Edwards OneWorld permite obtener acceso al sistema JD Edwards OneWorld desde un sistema [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Este adaptador pertenece a un grupo de ocho adaptadores de línea empresarial (LOB) que Microsoft distribuye para su uso con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
 El trabajo de práctico de JD Edwards OneWorld se divide en dos partes. La primera práctica (Práctica 1) le permite usar el sistema JD Edwards OneWorld sin necesidad de contar con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o alguno de los productos de Microsoft. Podrá usar la herramienta JD Edwards OneWorld Client para conectarse a una base de datos de JD Edwards OneWorld y localizar registros específicos basados en direcciones.  
  
 En la segunda práctica (Práctica 2), creará un proyecto y una orquestación de BizTalk. Después de crear la aplicación, la implementará y usará para conectarse a un sistema JD Edwards OneWorld mediante el adaptador de JD Edwards OneWorld. El objetivo es obtener acceso a los datos a través de la aplicación BizTalk mediante el adaptador.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar el procedimiento de esta práctica, deberá instalar el software cliente de JD Edwards OneWorld y su actualización más reciente. Para usar las herramientas del software cliente, deberá tener una base de datos de JD Edwards OneWorld, conectividad de red para tal base de datos y una cuenta de usuario en ese sistema. No es necesario contar con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para completar esta práctica.  
  
## <a name="lab-1---using-a-jd-edwards-oneworld-system"></a>Práctica 1: uso del sistema JD Edwards OneWorld  
 En esta práctica, usará el sistema JD Edwards OneWorld sin necesidad de usar componentes de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Los objetivos son probar la conectividad con JD Edwards OneWorld y garantizar que la segunda práctica funcione correctamente. Usará la herramienta JD Edwards OneWorld SQL Plus para crear y manipular una tabla de datos en una base de datos de JD Edwards OneWorld.  
  
## <a name="procedures-for-lab-1---using-a-jd-edwards-oneworld-system"></a>Procedimientos para la Práctica 1: uso del sistema JD Edwards OneWorld  
  
#### <a name="to-log-on-to-jd-edwards-oneworld-by-using-a-browser"></a>Iniciar sesión en JD Edwards OneWorld mediante un explorador  
  
-   Inicie sesión en el sistema JD Edwards OneWorld haciendo clic en el icono JD Edwards OneWorld. Escriba su **Id. de usuario**, **contraseña**, y **entorno**y, a continuación, haga clic en **Aceptar**.  
  
     ![](../core/media/f04db2ef-d587-4357-b9e8-c96319886e97.gif "f04db2ef-d587-4357-b9e8-c96319886e97")  
  
#### <a name="to-locate-and-view-jd-edwards-oneworld-data"></a>Localizar y ver datos de JD Edwards OneWorld  
  
1.  Si inicia sesión correctamente, mostrará el **JD Edwards OneWorld Explorer**.  
  
     ![](../core/media/14e8c206-7e38-48f8-9108-e32a7ac9a740.gif "14e8c206-7e38-48f8-9108-e32a7ac9a740")  
  
2.  Expanda **directorio maestro**, a continuación, **Foundation sistemas**, a continuación, **libreta de direcciones**y, a continuación, **procesamiento diario**.  
  
     ![](../core/media/1f742221-00e5-4697-95ff-64aa63ed567a.gif "1f742221-00e5-4697-95ff-64aa63ed567a")  
  
3.  En la ventana de la derecha, haga doble clic en **revisiones de la libreta de direcciones**.  
  
     ![](../core/media/a6d4e871-9c9c-4bc0-9c4f-4bdfd7cc5031.gif "a6d4e871-9c9c-4bc0-9c4f-4bdfd7cc5031")  
  
4.  Para **nombre alfa**, escriba `Ga`, seleccione la **para mostrar la dirección** casilla de verificación y, a continuación, haga clic en **buscar** en la barra de herramientas.  
  
     ![](../core/media/2f58413f-41a9-4ed9-ba5c-1d6d59eafb01.gif "2f58413f-41a9-4ed9-ba5c-1d6d59eafb01")  
  
     En el **revisiones de la libreta de direcciones - [trabajar con direcciones]** cuadro de diálogo, se muestran dos registros como resultado de la búsqueda.  
  
     ![](../core/media/9284df4e-ca9b-48ab-b2bf-a90d765d4a05.gif "9284df4e-ca9b-48ab-b2bf-a90d765d4a05")  
  
     Un método alternativo de localización de datos es borrar la **nombre alfa** , a continuación, haga clic en el cuadro de texto anterior la **número de dirección** columna y escriba `500`. Haga clic en **buscar** en la barra de herramientas para mostrar los resultados de búsqueda.  
  
     ![](../core/media/a88bd867-9a16-416a-a43e-cdfcc65fc670.gif "a88bd867-9a16-416a-a43e-cdfcc65fc670")  
  
     En la práctica 2, se proporcionarán instrucciones para usar el adaptador de JD Edwards OneWorld para recuperar la información de un **número de dirección** de `500`.  
  
5.  En el **archivo** menú, haga clic en **salir** para salir de la sesión de JD Edwards OneWorld Client.  
  
## <a name="summary"></a>Resumen  
 En esta práctica, usó la herramienta JD Edwards OneWorld Client para iniciar sesión en el sistema JD Edwards OneWorld. Una vez establecida la conexión, buscó datos específicos y vio los registros de datos devueltos por la búsqueda.