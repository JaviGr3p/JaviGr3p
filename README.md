import { useState } from "react";
import { motion } from "framer-motion";
import { FaTerminal } from "react-icons/fa";

export default function Portfolio() {
  const [activeSection, setActiveSection] = useState("home");

  const sections = {
    home: "Especialista en Ciberseguridad y Pentesting. Explora mis proyectos y conocimientos.",
    proyectos: "Aquí encontrarás algunos de mis trabajos en pentesting, herramientas y más.",
    contacto: "Puedes contactarme a través de mis redes sociales o correo electrónico."
  };

  return (
    <div className="bg-black text-green-400 min-h-screen flex flex-col items-center justify-center font-mono p-5">
      <motion.div
        initial={{ opacity: 0, scale: 0.8 }}
        animate={{ opacity: 1, scale: 1 }}
        transition={{ duration: 0.5 }}
        className="text-center"
      >
        <FaTerminal className="text-5xl mb-4" />
        <h1 className="text-4xl font-bold">Bienvenido a mi Portafolio</h1>
      </motion.div>
      
      <div className="mt-6 flex space-x-6">
        {Object.keys(sections).map((section) => (
          <button 
            key={section} 
            onClick={() => setActiveSection(section)}
            className="border border-green-400 px-4 py-2 rounded hover:bg-green-400 hover:text-black transition-all"
          >
            {section.charAt(0).toUpperCase() + section.slice(1)}
          </button>
        ))}
      </div>
      
      <div className="mt-6 text-lg text-center max-w-lg">
        {sections[activeSection]}
      </div>
    </div>
  );
}
