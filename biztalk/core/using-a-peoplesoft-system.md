---
title: Usar un sistema PeopleSoft | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c228ac23-184f-4c08-922b-ba84f5f2c52f
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c93e025ddb2ccec4b0088c20837a4f307f40aada
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="using-a-peoplesoft-system"></a>Usar un sistema PeopleSoft
Se puede obtener acceso al sistema PeopleSoft desde un sistema [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] mediante el adaptador de PeopleSoft. Este adaptador pertenece a un grupo de ocho adaptadores de línea empresarial (LOB) que Microsoft distribuye para su uso con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
 El trabajo práctico de PeopleSoft se divide en dos partes. Esta primera práctica (Práctica 1) le permite usar el sistema PeopleSoft sin necesidad de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ni de ningún otro producto de Microsoft (salvo quizás Internet Explorer, pero puede usar cualquier explorador). En esta práctica, se conectará al sistema PeopleSoft para localizar y modificar un sencillo registro de datos.  
  
 En la segunda práctica (Práctica 2), creará un proyecto y una orquestación de BizTalk. Después de crear la aplicación, la implementará y usará para conectarse a un sistema PeopleSoft mediante el adaptador de PeopleSoft. El objetivo es obtener acceso a los datos a través de la aplicación BizTalk mediante el adaptador.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar los procedimientos de esta práctica, necesita un explorador y una conexión a Internet, junto con una cuenta de usuario en un sistema PeopleSoft. Debe conocer la ubicación que hay que examinar para obtener acceso web al sistema PeopleSoft. NO necesita [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ni ninguna otra tecnología de Microsoft.  
  
## <a name="lab-1---using-a-peoplesoft-system"></a>Práctica 1: uso de un sistema PeopleSoft  
 En esta práctica, usará el sistema PeopleSoft sin emplear ningún componente de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. El objetivo es probar su conexión con PeopleSoft para garantizar que la segunda práctica funcione correctamente. Inicialmente, se conectará al sistema PeopleSoft a través de su interfaz web, que le permite iniciar sesión a través de un explorador como, por ejemplo, Internet Explorer.  
  
## <a name="procedures-for-lab-1---using-a-peoplesoft-system"></a>Procedimientos para la Práctica 1: uso de un sistema PeopleSoft  
  
#### <a name="to-log-on-to-peoplesoft-by-using-a-browser"></a>Para iniciar sesión en PeopleSoft a través de un explorador  
  
-   Vaya a una página de inicio de sesión de PeopleSoft para iniciar sesión en el sistema PeopleSoft. Escriba su **Id. de usuario** y **contraseña** y, a continuación, haga clic en **inicio de sesión**.  
  
     ![](../core/media/1e3e5c0f-316b-4aa3-946e-3bb3665b0ddb.gif "1e3e5c0f-316b-4aa3-946e-3bb3665b0ddb")  
  
#### <a name="to-locate-and-modify-peoplesoft-data"></a>Para localizar y modificar datos de PeopleSoft  
  
1.  Si inicia sesión correctamente, obtendrá acceso a la página que permite personalizar el contenido y elegir su diseño. Desplácese hacia abajo y expanda **establecer Financials/Supply Chain**, haga clic en **definiciones comunes**, haga clic en **ubicación**y, a continuación, haga clic en **ubicación** volver a ejecutarlo. Aparecerá la **ubicación** interfaz de búsqueda.  
  
     ![](../core/media/62a89cd4-464c-42fd-91cd-60ceeab5b006.gif "62a89cd4-464c-42fd-91cd-60ceeab5b006")  
  
2.  Para comenzar la búsqueda, establezca **SetID** a  **=** , establezca **Location Code** a **comienza con**, escriba **un**y, a continuación, haga clic en **búsqueda**. Se mostrarán las ciudades cuyos nombres comienzan con en el **resultados de la búsqueda** sección de la interfaz.  
  
     ![](../core/media/86661144-c666-4d72-9227-9f17df715ba4.gif "86661144-c666-4d72-9227-9f17df715ba4")  
  
3.  Haga clic en una de las ubicaciones para obtener su información detallada. Por ejemplo, en la ilustración siguiente, el usuario hace clic en el **AUS01** vincular en el **Location Code** columna.  
  
4.  Escriba datos nuevos en uno de los campos (como el **dirección 2** campo) y haga clic en **guardar** en la esquina inferior izquierda. En el registro se guardarán los datos recién especificados.  
  
     ![](../core/media/b6eb137c-c0b0-4906-8fbd-1bc036069fb0.gif "b6eb137c-c0b0-4906-8fbd-1bc036069fb0")  
  
5.  Para comprobar si se el cambio se realizó correctamente, repita el proceso desde el paso 2, busque de nuevo el mismo registro y observe los cambios realizados en él.  
  
6.  En la parte superior derecha de la ventana, haga clic en **cerrar sesión** para finalizar la sesión de PeopleSoft.  
  
     ![](../core/media/7760b541-5155-453e-a682-4780412f3c13.gif "7760b541-5155-453e-a682-4780412f3c13")  
  
    > [!NOTE]
    >  En la práctica siguiente se incluye instrucciones para usar el adaptador de PeopleSoft con el fin de recuperar la información para el registro de ubicación (AUS01) que ha modificado.  
  
## <a name="summary"></a>Resumen  
 En esta práctica inició sesión en el sistema PeopleSoft a través de un explorador. Una vez conectado, buscó datos y ha manipulado y actualizó el campo de dirección de un registro. Después de validar el cambio, pudo ver los datos modificados en el explorador para comprobar que el cambio se había ejecutado correctamente.