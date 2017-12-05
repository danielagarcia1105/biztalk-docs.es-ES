---
title: "Consideraciones internacionales para diseñar aplicaciones de BizTalk | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9daaaaf7-6149-4e62-9e9b-b6356fc820d2
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7ef22467c18580219e8587d63017d8bf146090d4
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="international-considerations-for-designing-biztalk-applications"></a>Consideraciones internacionales para diseñar aplicaciones de BizTalk
Se recomienda encarecidamente que revise los siguientes problemas conocidos cuando implemente las aplicaciones internacionales de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
 **Restricciones de caracteres para los nombres de equipo**  
  
 Instalar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no se admite en equipos con nombres que contienen caracteres no recogidos en el siguiente conjunto: letras (a Z, a z), dígitos (0-9), guiones (-) y caracteres de subrayado (_). Solo se admiten nombres de equipo que contengan los caracteres incluidos en este conjunto.  
  
 **Caracteres no aparezcan correctamente o no aparecen en absoluto debido a incorrectas de fuente y la configuración de reserva de fuente**  
  
 Puede experimentar problemas al visualizar caracteres (tales como los caracteres checos) en las herramientas de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] hospedadas en Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]. Para solucionar estos problemas, es posible que deba modificar la configuración de fuente disponible en la pestaña Opciones de Visual Studio y seleccionar otra fuente que sepa que admite los caracteres. Puede seleccionar Tahoma o Microsoft Sans Serif como la fuente predeterminada para las que se proporcionan capacidades de reserva de fuente.  
  
 **Caracteres de pares suplentes muestran como cuadrados en la consola de administración de BizTalk Server y otro servidor de BizTalk herramientas**  
  
 Es posible que no se puedan mostrar caracteres de pares suplentes en la consola de administración y en otras herramientas de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Los pares suplentes son una representación de caracteres codificados para un único carácter abstracto que se compone de una secuencia de dos unidades de código. Asegúrese de que tiene la fuente adecuada instalada en el sistema (se incluye en las versiones de chino de Office XP y 2003). Es posible que sea necesario también cambiar las opciones de fuente de las herramientas que tienen dicha capacidad (por ejemplo, [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]).  
  
 En otras herramientas que no tengan una opción para configurar fuentes, los caracteres de pares suplentes se mostrarán como cuadrados, tal como la consola de administración. Si ve cuadrados, los caracteres no están dañados; simplemente no pueden mostrarse correctamente debido a la falta de compatibilidad de fuentes.  
  
 **Limitaciones de caracteres de servicios Web**  
  
 Si tiene intención de publicar una orquestación como un Servicio Web, es posible que le surjan problemas con los caracteres que se usan en los nombres de orquestaciones y de puertos ya que éstos se usan en los nombres de archivo de Servicios Web (archivos .asmx) y el directorio virtual, en el Asistente para publicación de servicios Web. Solo Servicios de Microsoft Internet Information Server (IIS) 7.0 (que se incluye en Microsoft Windows Server 2008 y Windows Vista) admite totalmente caracteres Unicode. Por lo tanto, si usa una versión anterior de IIS o Windows, los nombres de las orquestaciones, de los puertos, de los servicios Web y de los directorios virtuales solo deben incluir caracteres ANSI admitidos por la versión del idioma de Windows (por ejemplo, no se permiten caracteres de japonés en una versión de Windows en inglés).  
  
 Tenga en cuenta también que para servicios Web en los nombres de proyecto [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] están restringidos a caracteres ASCII.  
  
 **Trabajar con distintas codificaciones de documentos**  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]admite varias codificaciones diferentes para XML y documentos de archivo sin formato, por ejemplo UTF-16, UTF-8, chino simplificado GBK, chino simplificado GB18030 y así sucesivamente.  
  
 Para los documentos entrantes, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] puede reconocer la declaración de codificación en documentos XML, como "\<? versión xml ="1.0"encoding ="GB2312"?\>". El esquema de archivo sin formato tiene un **página de códigos** propiedad para indicar la codificación de los documentos de archivo sin formato entrante.  
  
 Para los documentos de salida, XML y ensambladores de archivos sin utilizar el **juego de caracteres de destino** propiedad. Si se especifica esta propiedad, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] convierte los documentos salientes en el juego de caracteres especificado, independientemente de cuál sea el original. Si no hay ningún **juego de caracteres de destino** propiedad está establecida, XML usa el protocolo UTF-8 y archivos sin formato usan la página de códigos especificada en el esquema de archivo sin formato.  
  
 **Conversión de código de una página de códigos no admitida a una página de códigos de Windows**  
  
 Para implementar conversiones de código de páginas de código no admitidas en una página de códigos de Windows, debe crear un componente de canalización personalizado.  
  
 **Impacto de la marca de orden de bytes en la codificación del documento**  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] determina la codificación de caracteres y produce documentos con una codificación de caracteres determinada de forma diferente a los mensajes XML y a archivos sin formato.  
  
 **Editor de esquemas puede contener propiedades en más de un idioma**  
  
 Los nombres de propiedad del Lenguaje de definición de esquemas XML (XSD) que se muestran en la ventana Propiedades del Editor de esquemas y en el código fuente XML no están localizados y aparecen en inglés en todas las versiones localizadas. El resto de propiedades se muestran en el idioma local. Por ejemplo, en la versión en chino simplificada de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], las propiedades de esquema están disponibles en inglés, pero otras propiedades se muestran en chino.  
  
 **Datos que dependen de la configuración regional en archivos planos**  
  
 Numerosas configuraciones regionales representan datos como la fecha, la hora, el número y la moneda mediante formatos distintos a los que se definen en el estándar XML. Por ejemplo, varias configuraciones regionales usan un separador decimal que no es un punto (.), por lo que el número cinco y tres cuartos se puede representar como 5,75.  
  
 En [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], todos los campos de planos, archivos, excepto la fecha y hora se tratan como cadenas, por lo que el análisis se realice correctamente. Sin embargo, cuando se usa la validación XML, el mensaje XML resultante genera errores durante la validación con respecto al esquema.  
  
 Para los campos de fecha y hora, el analizador intenta examinar el valor del campo para la instancia DateTime mediante un formato de fecha u hora personalizado si está definido y lo escribe en formato XML o usa el valor original como una cadena si el formato de fecha u hora no está definido. De nuevo, si se usa la validación XML, es posible que se generen errores en la validación de la fecha y hora resultantes si no se usa un formato de fecha u hora personalizado y si el valor del campo que se usó en el mensaje de archivo sin formato no estaba en el formato XML correcto de fecha u hora.  
  
 Tenga en cuenta que puede crear también componentes de canalización personalizados o asignaciones para actualizar los valores de campo y así producir XML válido.  
  
 **Compatibilidad de lenguaje de definición de BAM**  
  
 Antes de poder implementar un archivo XML de definición de BAM, debe asegurarse de que el idioma que se usa para crear este archivo coincide con la configuración regional del equipo en el que lo está implementando. Si la configuración del archivo y la del equipo no coinciden, debe reiniciar primero el equipo que se usó para ejecutar el archivo BM.exe.  
  
> [!NOTE]
>  El archivo XML de definición de BAM no puede contener texto en varios idiomas, a no ser que todos los idiomas utilicen la misma página de códigos, o que solo se incluyan dos idiomas y que uno de ellos sea el inglés.  
  
## <a name="see-also"></a>Vea también  
 [Implementación de codificación de caracteres en un componente de canalización](../core/implementing-character-encoding-in-a-pipeline-component.md)   
 [Controlar la codificación en un componente de canalización de desensamblador](../core/handling-encoding-in-a-disassembler-pipeline-component.md)   
 [Codificación de caracteres en el componente de canalización de desensamblador de archivos sin formato](../core/character-encoding-in-the-flat-file-disassembler-pipeline-component.md)   
 [Codificación de caracteres en el componente de canalización de ensamblador de archivo sin formato](../core/character-encoding-in-the-flat-file-assembler-pipeline-component.md)   
 [Codificación de caracteres en el componente de canalización de ensamblador XML](../core/character-encoding-in-the-xml-assembler-pipeline-component.md)   
 [Codificación de caracteres en componentes de canalización de desensamblador XML](../core/character-encoding-in-xml-disassembler-pipeline-component.md)