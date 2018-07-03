---
title: Preguntas y respuestas de solución de problemas generales | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d2f89d92-0a97-4017-8b8e-6afd8b20eaf4
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6a47cfd0bc1d2de1ad044712c12b97260981e610
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010653"
---
# <a name="general-troubleshooting-questions-and-answers"></a>Preguntas y respuestas generales de solución de problemas
En este tema se incluyen preguntas y respuestas para ayudarle a resolver problemas con el Asignador de BizTalk.  
  
## <a name="how-do-i-specify-xslt-output-settings"></a>¿Cómo especifico la configuración de salida XSLT?  
 Puede usar el Asignador de BizTalk para incluir u omitir declaraciones XML y controlar la codificación usada para los datos de instancia de salida.  
  
#### <a name="include-or-exclude-an-xml-declaration"></a>Incluir o excluir una declaración XML  
  
1.  En la vista Cuadrícula, haga clic en la cuadrícula del Asignador. El **propiedades** ventana muestra las propiedades de la cuadrícula.  
  
2.  En la lista desplegable para la **omitir declaración XML** propiedad, seleccione **Sí** para omitir una declaración XML, o bien seleccione **No** no para omitir una declaración XML.  
  
#### <a name="set-encoding-for-output-instance-data"></a>Establecer la codificación de datos de instancia de salida  
  
1.  En la vista Cuadrícula, haga clic en la cuadrícula del Asignador. El **propiedades** ventana muestra las propiedades de la cuadrícula.  
  
2.  En la lista desplegable para la **codificación XSLT** propiedad, seleccione el juego de caracteres desea usar para los datos de instancia de salida.  
  
## <a name="how-do-i-create-multipart-mappings"></a>¿Cómo creo asignaciones de varias partes?  
 Si tiene varias asignaciones que se usan juntas, necesitará combinarlas en una orquestación mediante el **transformar** forma para probarlas conjuntamente. El Asignador de BizTalk solo puede probar una asignación cada vez.  
  
## <a name="why-isnt-my-database-functoid-working"></a>¿Por qué mi functoid de bases de datos no funciona?  
 Los functoids de base de datos **búsqueda de la base de datos** y **Extractor de valor** no devuelven directamente información de error; en su lugar, capturan la información y para proporcionar el **dedevolucióndeError** functoid para su uso por la asignación. Puede usar el **devolución de Error** functoid para la detección de errores en los escenarios siguientes:  
  
- Cuando la asignación tiene un **búsqueda de la base de datos** o **Extractor de valor** functoid que no se comporta según lo previsto. Para ver el mensaje de error, asigne de forma temporal el functoid a un campo en el esquema de salida.  
  
- Si su aplicación espera otro contenido de mensaje cuando se producen errores en las operaciones de la base de datos. Puede usar el **devolución de Error** functoid para detectar un error y el mensaje de error se asignan a una estructura alternativa para que las aplicaciones de nivel inferiores pueden reaccionar de manera controlada.  
  
  Para evitar errores que se detectan en tiempo de ejecución, asegúrese de que el primer parámetro para el **devolución de Error** functoid es el resultado de una **búsqueda de la base de datos** functoid y no la salida de otro functoid en la Categoría de la base de datos.  
  
  Para obtener más información sobre el uso de la **devolución de Error** functoid (incluido un ejemplo), consulte el **referencia de Functoid** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].
  
## <a name="why-is-my-map-failing-when-calling-my-custom-functoid"></a>¿Por qué se producen errores en mi asignación cuando llamo a mi functoid personalizado?  
 Los functoids personalizados debe estar instalados en la caché de ensamblados global (GAC) en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] equipo antes de que se pueden invocar en un mapa. Compruebe que en ensamblado que contiene el functoid personalizado se ha firmado y colocado en la GAC. Copie también el ensamblado en la carpeta “%BTSINSTALLPATH%\Developer Tools\Mapper Extensions”.  
  
 Para obtener más información acerca de cómo instalar ensamblados en la GAC, consulte [instalación del ensamblado en la GAC](../core/assembly-installation-in-the-gac.md). Para ver los ensamblados instalados en la GAC, desplácese al directorio del ensamblado de su [!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)] directorio de instalación.  
  
## <a name="see-also"></a>Vea también  
 [Solución de problemas de mapas](../core/troubleshooting-maps.md)