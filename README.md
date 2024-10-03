"use client"

import React, { useState } from 'react'
import Image from 'next/image'
import { FaLinkedin, FaGithub, FaEnvelope } from 'react-icons/fa'

import { Button } from "@/components/ui/button"
import { Card, CardContent, CardDescription, CardHeader, CardTitle } from "@/components/ui/card"
import { Progress } from "@/components/ui/progress"

export default function PortfolioResponsive() {
  const [activeSection, setActiveSection] = useState('about')
  const [isContactOpen, setIsContactOpen] = useState(false)

  return (
    <div className="flex min-h-screen bg-gray-900 text-gray-100">
      <div className="w-[30%] bg-gray-800 p-4 flex flex-col">
        <div className="relative w-full pb-[100%] mb-4">
          <Image
            src="/placeholder.svg?height=300&width=300"
            alt="Andrés Vergara"
            layout="fill"
            objectFit="cover"
            className="rounded-full border-4 border-teal-500"
          />
        </div>
        <h1 className="text-2xl font-bold mb-4 text-teal-300">Andrés Vergara</h1>
        <nav className="space-y-2">
          <Button 
            variant="ghost" 
            className="w-full justify-start p-0 text-gray-300 hover:text-teal-300 hover:bg-gray-700"
            onClick={() => {setActiveSection('about'); setIsContactOpen(false)}}
          >
            <span className="text-lg font-semibold">Sobre mí</span>
          </Button>
          <Button 
            variant="ghost" 
            className="w-full justify-start p-0 text-gray-300 hover:text-teal-300 hover:bg-gray-700"
            onClick={() => {setActiveSection('projects'); setIsContactOpen(false)}}
          >
            <span className="text-lg font-semibold">Proyectos</span>
          </Button>
          <Button 
            variant="ghost" 
            className="w-full justify-start p-0 text-gray-300 hover:text-teal-300 hover:bg-gray-700"
            onClick={() => setIsContactOpen(!isContactOpen)}
          >
            <span className="text-lg font-semibold">Contacto</span>
          </Button>
        </nav>
        {isContactOpen && (
          <div className="mt-4 space-y-2">
            <Button variant="outline" className="w-full flex items-center justify-start bg-gray-700 text-teal-300 hover:bg-gray-600">
              <FaLinkedin className="mr-2 h-4 w-4" />
              <a href="https://www.linkedin.com/in/tu-perfil" target="_blank" rel="noopener noreferrer">
                LinkedIn
              </a>
            </Button>
            <Button variant="outline" className="w-full flex items-center justify-start bg-gray-700 text-teal-300 hover:bg-gray-600">
              <FaGithub className="mr-2 h-4 w-4" />
              <a href="https://github.com/tu-usuario" target="_blank" rel="noopener noreferrer">
                GitHub
              </a>
            </Button>
            <Button variant="outline" className="w-full flex items-center justify-start bg-gray-700 text-teal-300 hover:bg-gray-600">
              <FaEnvelope className="mr-2 h-4 w-4" />
              <a href="mailto:tu@email.com">
                Email
              </a>
            </Button>
          </div>
        )}
      </div>

      <div className="flex-1 p-8 overflow-y-auto bg-gray-900">
        {activeSection === 'about' && (
          <section id="about">
            <h2 className="text-3xl font-bold mb-4 text-teal-300">Sobre mí</h2>
            <p className="text-lg mb-6 text-gray-300">
              Apasionado por la informática. Me encantaría trabajar en el sector TI. 
              Actualmente me encuentro aprendiendo Python e inteligencia artificial. 
              Aspiro con el tiempo a poder desarrollar un rol de científico de datos 
              u operaciones de machine learning.
            </p>
            <p className="text-lg mb-6 text-gray-300">
              Como Técnico superior en sistemas de telecomunicaciones e informáticos, 
              tengo una sólida base en redes, sistemas operativos y programación. 
              Mi formación me ha proporcionado habilidades prácticas en el diseño, 
              implementación y mantenimiento de sistemas de comunicación.
            </p>
            <p className="text-lg mb-6 text-gray-300">
              Mi interés por la inteligencia artificial y el machine learning me ha 
              llevado a profundizar en Python y sus bibliotecas relacionadas con 
              el análisis de datos y el aprendizaje automático. Estoy constantemente 
              buscando oportunidades para aplicar estos conocimientos en proyectos 
              prácticos y desafiantes.
            </p>
            <div className="mt-8">
              <h3 className="text-2xl font-semibold mb-4 text-teal-300">Habilidades</h3>
              <div className="space-y-4">
                <div>
                  <div className="flex justify-between mb-1 text-gray-300">
                    <span>Python</span>
                    <span>80%</span>
                  </div>
                  <Progress value={80} className="w-full bg-gray-700" indicatorClassName="bg-teal-500" />
                </div>
                <div>
                  <div className="flex justify-between mb-1 text-gray-300">
                    <span>Machine Learning</span>
                    <span>60%</span>
                  </div>
                  <Progress value={60} className="w-full bg-gray-700" indicatorClassName="bg-teal-500" />
                </div>
                <div>
                  <div className="flex justify-between mb-1 text-gray-300">
                    <span>Telecomunicaciones</span>
                    <span>90%</span>
                  </div>
                  <Progress value={90} className="w-full bg-gray-700" indicatorClassName="bg-teal-500" />
                </div>
                <div>
                  <div className="flex justify-between mb-1 text-gray-300">
                    <span>Redes</span>
                    <span>85%</span>
                  </div>
                  <Progress value={85} className="w-full bg-gray-700" indicatorClassName="bg-teal-500" />
                </div>
                <div>
                  <div className="flex justify-between mb-1 text-gray-300">
                    <span>Sistemas Operativos</span>
                    <span>75%</span>
                  </div>
                  <Progress value={75} className="w-full bg-gray-700" indicatorClassName="bg-teal-500" />
                </div>
              </div>
            </div>
          </section>
        )}

        {activeSection === 'projects' && (
          <section id="projects">
            <h2 className="text-3xl font-bold mb-4 text-teal-300">Proyectos</h2>
            <div className="grid grid-cols-1 md:grid-cols-2 gap-4">
              <Card className="bg-gray-800 border-gray-700">
                <CardHeader>
                  <CardTitle className="text-teal-300">Análisis de Datos de Ventas</CardTitle>
                  <CardDescription className="text-gray-400">Python, Pandas, Matplotlib</CardDescription>
                </CardHeader>
                <CardContent className="text-gray-300">
                  <p>Desarrollé un script en Python para analizar y visualizar datos de ventas de una empresa. Utilicé Pandas para la manipulación de datos y Matplotlib para crear gráficos interactivos que muestran tendencias y patrones en las ventas.</p>
                </CardContent>
              </Card>
              <Card className="bg-gray-800 border-gray-700">
                <CardHeader>
                  <CardTitle className="text-teal-300">Predicción de Tráfico en Redes</CardTitle>
                  <CardDescription className="text-gray-400">Machine Learning, Python, Scikit-learn</CardDescription>
                </CardHeader>
                <CardContent className="text-gray-300">
                  <p>Implementé un modelo de machine learning para predecir el tráfico en redes de telecomunicaciones. Utilicé datos históricos para entrenar el modelo y logré una precisión del 85% en la predicción de picos de tráfico.</p>
                </CardContent>
              </Card>
              <Card className="bg-gray-800 border-gray-700">
                <CardHeader>
                  <CardTitle className="text-teal-300">Sistema de Monitoreo de Red</CardTitle>
                  <CardDescription className="text-gray-400">Python, SNMP, Dashboard Web</CardDescription>
                </CardHeader>
                <CardContent className="text-gray-300">
                  <p>Desarrollé un sistema de monitoreo de red utilizando Python y el protocolo SNMP. El sistema recopila datos de dispositivos de red y los presenta en un dashboard web en tiempo real, permitiendo una fácil identificación de problemas.</p>
                </CardContent>
              </Card>
              <Card className="bg-gray-800 border-gray-700">
                <CardHeader>
                  <CardTitle className="text-teal-300">Automatización de Configuración de Routers</CardTitle>
                  <CardDescription className="text-gray-400">Python, Paramiko, Cisco IOS</CardDescription>
                </CardHeader>
                <CardContent className="text-gray-300">
                  <p>Creé un script de Python que automatiza la configuración de múltiples routers Cisco. El script utiliza Paramiko para establecer conexiones SSH seguras y aplicar configuraciones predefinidas, reduciendo significativamente el tiempo de implementación.</p>
                </CardContent>
              </Card>
            </div>
          </section>
        )}
      </div>
    </div>
  )
}
