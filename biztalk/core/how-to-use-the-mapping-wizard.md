---
title: Cómo usar el Asistente para asignación | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 35b96cea-ead7-43de-8411-62d2c7d6620e
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a6b016eb0599924d4927868b6a19d3b57389e5c9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257364"
---
# <a name="how-to-use-the-mapping-wizard"></a>Cómo usar el Asistente para asignaciones
Esta versión de Inicio de sesión único empresarial incluye el Asistente para asignaciones, que permite crear asignaciones de forma sencilla para aplicaciones afiliadas.  
  
> [!NOTE]
>  Sólo puede usar el Asistente para asignaciones si el UserID externo está basado en la cuenta de dominio de Windows.  
  
### <a name="to-start-the-mapping-wizard"></a>Para iniciar el Asistente para asignaciones  
  
1.  Abra el Inicio de sesión único empresarial.  
  
2.  En el panel de ámbito, haga clic en **aplicaciones afiliadas**.  
  
3.  Haga clic con el botón secundario en la aplicación afiliada correspondiente.  
  
4.  Haga clic en **crear asignaciones**. Aparecerá el Asistente para asignaciones.  
  
5.  **Asistente para la asignación**  
  
    -   Compruebe que se trata de la aplicación afiliada correcta y haga clic en **siguiente**.  
  
6.  **Opción del archivo de asignaciones** página  
  
    -   ENTSSO administra las asignaciones a través de un archivo XML. Puede elegir entre crear un archivo nuevo o usar uno existente.  
  
7.  **Ubicación de los archivos** página  
  
    -   Seleccione los archivos que se van a utilizar.  
  
    -   Debe hacer clic en **validar** para validar los archivos antes de continuar. El estado de validación aparece en la **estado** ventana.  
  
8.  **Cuentas** página  
  
    -   Elija una o varias cuentas para generar el archivo de asignaciones nuevo y haga clic en **validar**.  
  
9. **Nombre de usuario externo** página  
  
    -   Defina cómo se generará el nombre de usuario externo desde la cuenta de usuario de Windows. Cuando realice las selecciones en los cuadros, puede ver cómo aparecerán los nombres en el **ejemplo** cuadro.  
  
10. **Generar** página  
  
    -   Haga clic en **iniciar** para generar el archivo de asignaciones. (En la página siguiente, tendrá la oportunidad de ver o editar el archivo según sea necesario antes de que se creen las asignaciones). Los resultados se muestran en las tres ventanas siguientes.  
  
    -   El **número** de asignaciones en las cuentas seleccionadas es una aproximación, porque las cuentas pueden estar anidadas en otras cuentas.  
  
    -   Haga clic en **Ver archivo de registro** para examinar los errores o advertencias que pudieran haberse producido.  
  
11. **Opciones de** página  
  
    -   Su archivo se ha creado. Haga clic en **ver o editar el archivo de asignación** si lo desea.  
  
    -   Haga clic en **habilite las asignaciones de** si desea que las asignaciones que se habilitarán automáticamente. (Si no selecciona esta opción, tendrá que habilitarlas manualmente).  
  
    -   Haga clic en **establecer contraseña** para establecer automáticamente la contraseña para estas asignaciones.  
  
12. **Crear** página  
  
    -   Antes de crear las asignaciones, haga clic en **Ver archivo de asignaciones** si lo desea.  
  
    -   Cuando esté listo, haga clic en **iniciar** para realizar la operación de asignación. Su estado aparece en los tres cuadros siguientes.  
  
    -   Haga clic en **Ver archivo de registro** para examinar los errores o advertencias que pudieran haberse producido.  
  
13. **Pantalla Finalización del Asistente para asignaciones**  
  
14. Seleccione las opciones que desee y, a continuación, haga clic en **finalizar**.