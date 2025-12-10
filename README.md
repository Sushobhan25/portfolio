import React, { useState } from "react";
import { motion } from "framer-motion";

// PersonalPortfolio.jsx
// Single-file React component built with Tailwind CSS and Framer Motion.

export default function PersonalPortfolio() {
  const [projects] = useState([
    {
      id: 1,
      title: "Responsive Portfolio Website",
      desc: "A fast, accessible personal site built with React + Tailwind. Mobile-first, SEO-ready.",
      tech: ["React", "Tailwind", "Vercel"],
      repo: "#",
    },
    {
      id: 2,
      title: "To‑Do App (LocalStorage)",
      desc: "Task manager with add/edit/delete and persistent storage in browser.",
      tech: ["JavaScript", "React Hooks"],
      repo: "#",
    },
    {
      id: 3,
      title: "Landing Page UI Clone",
      desc: "Pixel-perfect static landing page with responsive grid and animations.",
      tech: ["HTML", "CSS", "Tailwind"],
      repo: "#",
    },
  ]);

  return (
    <div className="min-h-screen bg-gradient-to-b from-slate-900 to-slate-800 text-slate-100">
      <header className="max-w-5xl mx-auto p-6 flex flex-col md:flex-row items-center justify-between">
        <div>
          <h1 className="text-3xl md:text-4xl font-extrabold">Your Name</h1>
          <p className="mt-1 text-slate-300">B.Tech IT • Frontend Developer • React Enthusiast</p>
        </div>

        <nav className="mt-4 md:mt-0 flex gap-4">
          <a href="#projects" className="px-4 py-2 rounded-md bg-slate-700/40 hover:bg-slate-700/60">Projects</a>
          <a href="#skills" className="px-4 py-2 rounded-md bg-slate-700/40 hover:bg-slate-700/60">Skills</a>
          <a href="#contact" className="px-4 py-2 rounded-md bg-indigo-600 text-white hover:opacity-90">Contact</a>
        </nav>
      </header>

      <main className="max-w-5xl mx-auto px-6 py-8">
        {/* Hero */}
        <section className="grid md:grid-cols-2 gap-8 items-center">
          <motion.div
            initial={{ opacity: 0, y: 12 }}
            animate={{ opacity: 1, y: 0 }}
            transition={{ duration: 0.6 }}
            className="space-y-4"
          >
            <h2 className="text-2xl font-bold">Hi — I’m Your Name.</h2>
            <p className="text-slate-300">
              I build accessible, responsive user interfaces with a focus on clean code and
              delightful interactions. Currently a 2nd-year B.Tech IT student sharpening my frontend
              skills — React, Tailwind, and JavaScript.
            </p>

            <div className="flex gap-3 mt-2">
              <a href="#projects" className="inline-flex items-center px-4 py-2 bg-indigo-600 rounded-md">View Projects</a>
              <a href="#contact" className="inline-flex items-center px-4 py-2 border rounded-md">Get in touch</a>
            </div>
          </motion.div>

          <motion.div
            initial={{ scale: 0.98, opacity: 0 }}
            animate={{ scale: 1, opacity: 1 }}
            transition={{ duration: 0.6 }}
            className="bg-slate-900/40 p-6 rounded-2xl shadow-lg"
            aria-hidden
          >
            <p className="text-slate-400">Quick facts</p>
            <ul className="mt-4 grid grid-cols-2 gap-2 text-sm text-slate-300">
              <li className="bg-slate-800/60 p-3 rounded">📚 B.Tech IT — 2nd Year</li>
              <li className="bg-slate-800/60 p-3 rounded">💻 Focus: Frontend</li>
              <li className="bg-slate-800/60 p-3 rounded">⚡ Fast & Accessible UI</li>
              <li className="bg-slate-800/60 p-3 rounded">🌐 Deploys: Vercel / Netlify</li>
            </ul>
          </motion.div>
        </section>

        {/* Skills */}
        <section id="skills" className="mt-12">
          <h3 className="text-xl font-semibold">Skills</h3>
          <div className="mt-4 grid sm:grid-cols-2 md:grid-cols-4 gap-4">
            {[
              { name: "HTML & Accessibility" },
              { name: "Tailwind CSS" },
              { name: "React & Hooks" },
              { name: "JavaScript (ES6+)" },
              { name: "Git & GitHub" },
              { name: "Responsive Design" },
              { name: "Basic Node.js" },
              { name: "Problem Solving" },
            ].map((s) => (
              <div key={s.name} className="p-4 bg-slate-900/60 rounded-md">
                <p className="font-medium">{s.name}</p>
              </div>
            ))}
          </div>
        </section>

        {/* Projects */}
        <section id="projects" className="mt-12">
          <h3 className="text-xl font-semibold">Selected Projects</h3>
          <div className="mt-6 grid sm:grid-cols-2 gap-6">
            {projects.map((p) => (
              <motion.article
                key={p.id}
                initial={{ opacity: 0, y: 8 }}
                whileInView={{ opacity: 1, y: 0 }}
                viewport={{ once: true }}
                className="p-5 bg-slate-900/60 rounded-xl shadow"
              >
                <h4 className="text-lg font-semibold">{p.title}</h4>
                <p className="mt-2 text-slate-300 text-sm">{p.desc}</p>
                <div className="mt-3 flex flex-wrap gap-2">
                  {p.tech.map((t) => (
                    <span key={t} className="text-xs px-2 py-1 bg-slate-800/50 rounded">{t}</span>
                  ))}
                </div>
                <div className="mt-4 flex gap-3">
                  <a href={p.repo} className="text-sm underline">Repository</a>
                  <a href="#" className="text-sm underline">Live</a>
                </div>
              </motion.article>
            ))}
          </div>
        </section>

        {/* Contact */}
        <section id="contact" className="mt-12">
          <h3 className="text-xl font-semibold">Contact</h3>
          <div className="mt-4 grid md:grid-cols-2 gap-6">
            <div className="p-6 bg-slate-900/60 rounded-xl">
              <p className="text-slate-300">Want to collaborate or offer internship opportunities? Send a message — I reply quickly.</p>

              <form className="mt-4 space-y-3" onSubmit={(e) => e.preventDefault()}>
                <label className="block">
                  <span className="text-sm text-slate-300">Name</span>
                  <input className="mt-1 block w-full rounded-md bg-slate-800/40 p-2" placeholder="Your name" />
                </label>
                <label className="block">
                  <span className="text-sm text-slate-300">Email</span>
                  <input className="mt-1 block w-full rounded-md bg-slate-800/40 p-2" placeholder="you@email.com" />
                </label>
                <label className="block">
                  <span className="text-sm text-slate-300">Message</span>
                  <textarea className="mt-1 block w-full rounded-md bg-slate-800/40 p-2" rows={4} placeholder="Hi! I liked your project..." />
                </label>

                <div className="pt-2">
                  <button type="submit" className="px-4 py-2 bg-indigo-600 rounded-md">Send Message</button>
                </div>
              </form>
            </div>

            <aside className="p-6 bg-slate-900/40 rounded-xl">
              <h4 className="font-semibold">Connect</h4>
              <ul className="mt-3 text-slate-300 space-y-2">
                <li>Email: yourname@email.com</li>
                <li>GitHub: <a href="#" className="underline">github.com/yourusername</a></li>
                <li>LinkedIn: <a href="#" className="underline">linkedin.com/in/yourusername</a></li>
              </ul>

              <div className="mt-6">
                <a href="#" className="inline-block px-4 py-2 border rounded-md">Download Resume</a>
              </div>
            </aside>
          </div>
        </section>
      </main>

      <footer className="mt-12 py-6 border-t border-slate-700/30">
        <div className="max-w-5xl mx-auto px-6 text-center text-slate-400">© 2025 Your Name — Built with React & Tailwind</div>
      </footer>
    </div>
  );
}
