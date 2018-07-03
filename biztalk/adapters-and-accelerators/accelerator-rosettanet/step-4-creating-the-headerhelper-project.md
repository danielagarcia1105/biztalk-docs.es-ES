---
title: 'Paso 4: Creación del proyecto HeaderHelper | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- projects, helper projects
- private process tutorial, creating helper projects
ms.assetid: 82413537-032a-4368-8d77-d024a7c83b0b
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a01323dba6fba4673e4bcd2886df53d408421f9f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970797"
---
# <a name="step-4-creating-the-headerhelper-project"></a>Paso 4: Creación del proyecto HeaderHelper
En este paso, creará un [!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] biblioteca de clases. Cuando una orquestación de procesos privado, recibe un mensaje entrante, la biblioteca HeaderHelper determina si una conversión de documentos, es necesaria y si es necesario, realiza esa conversión. Esto permite que la orquestación trabajar con distintas versiones de documentos de RosettaNet Implementation Framework (RNIF). Además, cuando se envía un mensaje de respuesta de 3A2, la biblioteca HeaderHelper realiza una conversión de documentos adicional antes de transmitir el mensaje.  
  
### <a name="to-create-the-headerhelper-project"></a>Para crear el proyecto HeaderHelper  
  
1. En [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], en el Explorador de soluciones, haga clic en la solución de Contoso, seleccione **agregar**y, a continuación, haga clic en **nuevo proyecto**.  
  
2. En el cuadro de diálogo Agregar nuevo proyecto, en el panel tipos de proyecto, seleccione **Visual C#**.  
  
3. En el panel Plantillas, seleccione el **biblioteca de clases** plantilla.  
  
4. En el **nombre** , escriba **HeaderHelper**y, a continuación, haga clic en **Aceptar** para crear el proyecto.  
  
5. En el Explorador de soluciones, haga clic la **Class1.cs** de archivos en el **HeaderHelper** del proyecto, haga clic en **cambiar el nombre de**, tipo **HeaderHelper.cs**, y, a continuación, presione **ENTRAR**.  
  
### <a name="to-create-the-helper-class"></a>Para crear la clase auxiliar  
  
1.  En el Explorador de soluciones, expanda el **HeaderHelper** del proyecto y, a continuación, haga doble clic en el **HeaderHelper.cs** el nodo para abrir el archivo de origen HeaderHelper.  
  
2.  Escriba el código siguiente en el archivo de código fuente, sobrescribir todo el código existente:  
  
    ```  
    using System;  
    using System.Xml;  
  
    namespace ContosoPriceAndAvailability  
    {  
        public class Helper  
        {  
            static public XmlDocument NormalizeHeader( XmlDocument curPip )  
            {  
                string strInput = curPip.OuterXml;  
                try  
                {  
                    XmlDocument xDoc = new XmlDocument();  
  
                    strInput = strInput.Replace("<!DOCTYPE Pip3A2PriceAndAvailabilityQuery SYSTEM \"3A2PriceAndAvailabilityQueryMessageGuideline_v1_3.dtd\"[]>",String.Empty);  
                    strInput = strInput.Replace("<Pip3A2PriceAndAvailabilityQuery>","<Pip3A2PriceAndAvailabilityQuery xmlns=\"http://schemas.microsoft.com/biztalk/btarn/2004/3A2PriceAndAvailabilityQueryMessageGuideline_v1_3.dtd\">");  
                    strInput = strInput.Replace("xml:",String.Empty);  
                    strInput = strInput.Replace("b:",String.Empty);  
                    strInput = strInput.Replace("lang:",String.Empty);  
                    strInput = strInput.Replace("ns1:",String.Empty);  
  
                    xDoc.LoadXml(strInput);  
  
                    return xDoc;  
                }  
                catch(Exception ex)  
                {  
                    System.Diagnostics.Debug.Write( ex.Message );  
                    throw ex;  
                }  
            }  
  
            static public string ReturnSCWithDocType( XmlDocument xmlDoc )  
            {  
                try  
                {  
                    string sResponse = xmlDoc.InnerXml;  
                    sResponse=sResponse.Replace("ns0:",String.Empty);  
                    xmlDoc.LoadXml(sResponse);  
                    xmlDoc.DocumentElement.RemoveAllAttributes();  
                    sResponse = xmlDoc.InnerXml;  
  
                    sResponse = sResponse.Insert(0,"<!DOCTYPE Pip3A2PriceAndAvailabilityResponse SYSTEM \"3A2PriceAndAvailabilityResponseMessageGuideline_v1_3.dtd\">");  
                    sResponse = sResponse.Replace("ns0:",String.Empty);  
                    sResponse = sResponse.Replace("b:",String.Empty);  
                    sResponse = sResponse.Replace("lang:",String.Empty);  
                    sResponse = sResponse.Replace("ns1:",String.Empty);  
  
                    return sResponse;  
                }  
                catch(Exception ex)  
                {  
                    throw ex;  
                }  
            }  
        }  
    }  
    ```  
  
3.  En el menú **Archivo** , haga clic en **Guardar todo**.  
  
### <a name="to-create-a-strong-named-assembly-for-the-headerhelper-project"></a>Para crear un ensamblado con nombre seguro para el proyecto HeaderHelper  
  
1.  En el Explorador de soluciones, haga clic en el **HeaderHelper** del proyecto y, a continuación, haga clic en **propiedades**.  
  
2.  En el cuadro de diálogo páginas de propiedades HeaderHelper seleccione **firma** en el panel izquierdo del panel de propiedades de HeaderHelp.  
  
3.  En el panel derecho, haga clic en **firmar el ensamblado**.  
  
4.  Haga clic en el **elegir un archivo de clave de nombre seguro** cuadro de texto y, a continuación, seleccione **\<examinar\>** en la lista desplegable.  
  
5.  En el cuadro de diálogo Seleccionar archivo, desplácese a la ubicación del ensamblado de Contoso y haga doble clic en **FabConPriceAvail.snk**.  
  
6.  En el menú **Archivo** , haga clic en **Guardar todo**.  
  
7.  En el Explorador de soluciones, expanda el **HeaderHelper** del proyecto, expanda el **propiedades** nodo y, a continuación, haga doble clic en el **AssemblyInfo.cs** el nodo para abrir el AssemblyInfo.cs archivo de origen.  
  
8.  En el archivo AssemblyInfo.cs de origen, escriba el código siguiente en la línea después del atributo AssemblyCulture:  
  
    ```  
    [assembly: AssemblyKeyFile("../../../FabConPriceAvail.snk")]  
    ```  
  
9. En el menú **Archivo** , haga clic en **Guardar todo**.  
  
### <a name="to-build-and-deploy-the-headerhelper-project"></a>Para compilar e implementar el proyecto HeaderHelper  
  
1.  En el Explorador de soluciones, haga clic en el **HeaderHelper** del proyecto y, a continuación, haga clic en **compilar**.  
  
2.  Inicie un **símbolo del sistema de Visual Studio 2012**.  
  
3.  En el símbolo del sistema, desplácese a la ubicación de la **HeaderHelper** directorio de salida del proyecto (la carpeta \Bin\Debug).  
  
4.  En el símbolo del sistema, escriba **gacutil /if HeaderHelper.dll** y presione **ENTRAR** para instalar el **HeaderHelper** ensamblado en el **caché Global de ensamblados** .  
  
## <a name="see-also"></a>Vea también  
 [Paso 5: Modificación de la orquestación de procesos privados de Contoso](../../adapters-and-accelerators/accelerator-rosettanet/step-5-modifying-the-contoso-private-process-orchestration.md)