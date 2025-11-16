/*
AnimatedPortfolio.jsx
React component (single-file) that renders your portfolio/README content with animations.

How to use:
1. Make sure you have Tailwind CSS set up in your project.
2. Install framer-motion: `npm install framer-motion` or `yarn add framer-motion`.
3. Save this file as AnimatedPortfolio.jsx and import it into a page (e.g. App.jsx):
   `import AnimatedPortfolio from './AnimatedPortfolio'`
   `<AnimatedPortfolio />`
4. Optional: tweak colors, badges, or wording directly in the component.

Notes:
- This uses Tailwind utility classes for layout and styling and framer-motion for animations.
- If you want this as a Next.js page, wrap in a page file and ensure Tailwind is configured.
*/

import React from 'react'
import { motion } from 'framer-motion'

const container = {
  hidden: {},
  show: {
    transition: {
      staggerChildren: 0.12,
    },
  },
}

const fadeUp = {
  hidden: { opacity: 0, y: 10 },
  show: { opacity: 1, y: 0, transition: { duration: 0.6, ease: 'easeOut' } },
}

export default function AnimatedPortfolio() {
  return (
    <div className="min-h-screen bg-gradient-to-br from-gray-900 via-slate-900 to-gray-800 text-slate-100 p-6 flex items-center justify-center">
      <motion.article
        initial={{ opacity: 0, scale: 0.98 }}
        animate={{ opacity: 1, scale: 1 }}
        transition={{ duration: 0.6, ease: 'easeOut' }}
        className="max-w-4xl w-full bg-gradient-to-t from-white/3 via-white/5 to-white/2 backdrop-blur-md border border-white/6 rounded-2xl p-8 shadow-2xl"
      >
        <motion.header className="flex flex-col md:flex-row md:items-center md:justify-between gap-6" variants={container} initial="hidden" animate="show">
          <motion.div variants={fadeUp}>
            <h1 className="text-3xl md:text-4xl font-extrabold tracking-tight">Hi, I&apos;m <span className="text-transparent bg-clip-text bg-gradient-to-r from-indigo-300 via-pink-300 to-yellow-300">Binod Bist</span></h1>
            <p className="mt-1 text-slate-300">🎨 Frontend Web & Mobile Developer</p>
          </motion.div>

          <motion.div className="flex items-center gap-3" variants={fadeUp}>
            <a href="mailto:thebinodbist@gmail.com" className="inline-flex items-center gap-2 px-4 py-2 rounded-lg bg-white/6 hover:bg-white/10 transition">
              <svg xmlns="http://www.w3.org/2000/svg" className="h-5 w-5" viewBox="0 0 20 20" fill="currentColor"><path d="M2.94 5.5A2 2 0 014.75 4h10.5a2 2 0 011.81 1.5L10 9 2.94 5.5z" /><path d="M18 8.34V14a2 2 0 01-2 2H4a2 2 0 01-2-2V8.34l8 3.5 8-3.5z" /></svg>
              <span className="text-sm">thebinodbist@gmail.com</span>
            </a>
          </motion.div>
        </motion.header>

        <motion.section className="mt-8 grid md:grid-cols-3 gap-6" initial="hidden" animate="show" variants={container}>
          <motion.div className="md:col-span-2" variants={fadeUp}>
            <h2 className="text-xl font-semibold">About</h2>
            <p className="mt-2 text-slate-300 leading-relaxed">I’m a passionate <strong>Frontend Developer</strong> who loves crafting beautiful, responsive, and performant web and mobile interfaces using <em>React, Next.js, React Native, Tailwind CSS,</em> and <em>NativeWind</em>. My focus is on building user-friendly and visually appealing apps with clean, maintainable code.</p>

            <div className="mt-6">
              <h3 className="text-lg font-medium">What I do</h3>
              <ul className="mt-3 space-y-2 text-slate-300">
                <li>• Build <strong>modern, responsive UIs</strong> using React and Next.js</li>
                <li>• Create <strong>cross-platform mobile apps</strong> with React Native and NativeWind</li>
                <li>• Design with <strong>Tailwind CSS</strong> for fast, consistent UI</li>
                <li>• Focus on clean design, performance, and smooth UX</li>
              </ul>
            </div>

            <div className="mt-6">
              <h3 className="text-lg font-medium">Current Focus</h3>
              <p className="mt-2 text-slate-300">Mastering Next.js App Router, React Native, and exploring TypeScript and UI/UX optimization.</p>
            </div>
          </motion.div>

          <motion.aside className="space-y-4" variants={fadeUp}>
            <div className="rounded-xl p-4 bg-white/4 border border-white/6">
              <h4 className="font-semibold">Tech Stack & Skills</h4>
              <motion.div className="mt-3 flex flex-wrap gap-2" initial="hidden" animate="show" variants={container}>
                {['React','Next.js','JavaScript','Tailwind','React Native','Expo','NativeWind','Git','GitHub','VS Code'].map((tech, i) => (
                  <motion.span key={tech} variants={fadeUp} className="px-3 py-1 rounded-md text-sm bg-white/6 backdrop-blur-sm border border-white/6">
                    {tech}
                  </motion.span>
                ))}
              </motion.div>
            </div>

            <div className="rounded-xl p-4 bg-white/4 border border-white/6">
              <h4 className="font-semibold">Contact</h4>
              <p className="mt-2 text-slate-300">✉️ thebinodbist@gmail.com</p>
              <motion.a whileHover={{ scale: 1.03 }} whileTap={{ scale: 0.98 }} className="mt-3 inline-block text-sm px-3 py-2 bg-gradient-to-r from-indigo-500/30 to-pink-500/30 rounded-md border border-white/6" href="mailto:thebinodbist@gmail.com">Send a message</motion.a>
            </div>
          </motion.aside>
        </motion.section>

        <motion.div className="mt-8" variants={fadeUp}>
          <h3 className="text-lg font-semibold">Badges</h3>
          <p className="mt-2 text-slate-300">You can keep the shields images in your README — here are example placeholders integrated visually below for demo.</p>

          <div className="mt-4 flex flex-wrap gap-3">
            <motion.img variants={fadeUp} src="https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB" alt="React badge" className="h-8" />
            <motion.img variants={fadeUp} src="https://img.shields.io/badge/Next.js-000000?style=for-the-badge&logo=nextdotjs&logoColor=white" alt="Next badge" className="h-8" />
            <motion.img variants={fadeUp} src="https://img.shields.io/badge/Tailwind_CSS-06B6D4?style=for-the-badge&logo=tailwindcss&logoColor=white" alt="Tailwind badge" className="h-8" />
          </div>
        </motion.div>

        <motion.footer className="mt-8 text-center text-slate-400 text-sm" variants={fadeUp}>
          ⭐️ <em>"Designing experiences that feel as good as they look."</em>
        </motion.footer>
      </motion.article>

      {/* floating accent dots */}
      <svg className="pointer-events-none fixed -z-10 right-8 bottom-8 w-96 h-96 opacity-30" viewBox="0 0 600 600" fill="none" xmlns="http://www.w3.org/2000/svg">
        <defs>
          <linearGradient id="g" x1="0" x2="1">
            <stop offset="0" stopColor="#7c3aed" stopOpacity="0.18"></stop>
            <stop offset="1" stopColor="#ec4899" stopOpacity="0.08"></stop>
          </linearGradient>
        </defs>
        <circle cx="300" cy="300" r="200" stroke="url(#g)" strokeWidth="2" />
      </svg>
    </div>
  )
}
