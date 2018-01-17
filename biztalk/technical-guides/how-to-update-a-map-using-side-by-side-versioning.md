---
title: "Cómo actualizar un mapa con control de versiones en paralelo | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7b0e377f-92ab-483e-9f3c-222c7b5ac0b1
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6d463823a7038e1ead7e2de323da97eda372db76
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-update-a-map-using-side-by-side-versioning"></a>Cómo actualizar un mapa con control de versiones en paralelo
Algunos artefactos de BizTalk, como las asignaciones, se eligen por nombre seguro completo (FQSN), en cuyo caso los enlaces incluyen la versión utilizada. Esto permite que dos o más asignaciones pueden coexistir en paralelo en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración. Como resultado, puede seleccionar una de las asignaciones de entrada mapas en las propiedades de ubicación de recepción o de salida en las propiedades de puerto de envío.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar los procedimientos descritos en este tema, deberá iniciar la sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server.  
  
### <a name="to-add-a-second-map-side-by-side-to-an-existing-map"></a>Para agregar una segunda asignación en paralelo a una asignación existente  
  
1.  Abra Visual Studio y, a continuación, abra el proyecto que contiene la asignación.  
  
2.  Abra la asignación en el ensamblado y hace un cambio en la asignación de código.  
  
    > [!NOTE]  
    >  Si se llama a un mapa desde una orquestación y la referencia de asignación no es modificable, debe realizar cambios en el código en la propia orquestación.  
  
3.  Cambiar el número de versión del ensamblado:  
  
    1.  En el Explorador de soluciones, haga clic en el proyecto de BizTalk y, a continuación, haga clic en **propiedades**.  
  
    2.  En el **Diseñador de proyectos**, haga clic en el **aplicación** ficha.  
  
    3.  En el panel derecho, haga clic en **información de ensamblado**.  
  
    4.  En el **información de ensamblado** diálogo cuadro, especifique valores para la **versión del ensamblado** campo para cambiar el número de versión de ensamblado. Debe cambiar solo el número de versión principal o secundaria. El número de versión principal es el primer dígito en la secuencia (***n***. 0.0.0); el número de versión secundaria es el segundo dígito en la secuencia (0. ***n*** . 0.0).  
  
    5.  Haga clic en **Aceptar** para cerrar el **información de ensamblado** cuadro de diálogo.  
  
4.  Compile el ensamblado.  
  
5.  Implementar el ensamblado en el grupo (y todos los equipos).  
  
## <a name="modifying-a-map-to-reflect-updated-version-numbers"></a>Modificar una asignación para reflejar los números de versiones actualizados  
 Desde una asignación se pueden invocar los ensamblados .NET mediante el functoid Secuencias de comandos . Esto proporciona una gran flexibilidad y permite al programador resolver problemas de asignación personalizada muy diferentes. También impone una restricción unique en la asignación: internamente debe hacer referencia no solo el nombre de tipo de ensamblado, sino también el número de versión completo del ensamblado que se va a invocar. Como consecuencia, si cambia el número de versión del ensamblado al que llama la asignación, se interrumpirán todos los enlaces que hacen referencia al ensamblado.  
  
 Para evitar este problema, se recomienda que si se requieren que se llame desde un mapa de ensamblados, se crea un ensamblado específico para que contenga sólo la funcionalidad de mapas y que el número de versión de ensamblado de este ensamblado es fijo. De este modo, otras funciones auxiliares pueden actualizar la versión de ensamblado sin interrumpir las asignaciones.  
  
 Si se cambia un ensamblado al que hace referencia una asignación tras el desarrollo de la asignación, debería actualizar el archivo de asignaciones fuera del editor de asignaciones para que refleje los números de versiones actualizados.  
  
#### <a name="to-modify-a-map-file-to-reflect-updated-version-numbers"></a>Para modificar un archivo de asignación para que refleje los números de versión actualizada  
  
1.  Mediante el **iniciar** menú Abrir **el Bloc de notas**.  
  
2.  En **el Bloc de notas**, en la **archivo** menú, haga clic en **abiertos**. En el **abiertos** cuadro de diálogo, seleccione la asignación de archivos desea modificar y, a continuación, haga clic en **abiertos**.  
  
3.  En el menú **Edición** , haga clic en **Buscar**. En el **buscar** diálogo cuadro, escriba **ensamblado =**y, a continuación, haga clic en **Buscar siguiente**.  
  
4.  Si hay una referencia de secuencia de comandos a un ensamblado externo, el Bloc de notas debería buscar un elemento XML como el siguiente:  
  
    ```  
    <Script Language="ExternalAssembly" Assembly="Contoso.Scripts, Version=2.0.0.0, Culture=neutral, PublicKeyToken=  
    <token>  
    " Class="Contoso.Scripts" Function="CalculateValue" AssemblyPath="Contoso.Scripts.dll"/>  
    ```  
  
5.  Actualice el número de versión. Si hay varias instancias, use **reemplazar** en el **editar** menú.  
  
6.  Guarde el archivo.  
  
    > [!NOTE]  
    >  Podrá abrir la asignación mediante el editor de asignaciones.