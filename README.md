# ninjarobo87.github.io

import React, { useState, useEffect } from 'react';
import { 
  User, 
  Briefcase, 
  GraduationCap, 
  Award, 
  Code2, 
  Mail, 
  Phone, 
  MapPin, 
  ChevronRight, 
  ExternalLink,
  Bot,
  Cpu,
  Database,
  Terminal,
  Layers,
  Sparkles
} from 'lucide-react';

const App = () => {
  const [activeTab, setActiveTab] = useState('experience');
  const [scrolled, setScrolled] = useState(false);
  const [isVisible, setIsVisible] = useState(false);

  useEffect(() => {
    setIsVisible(true);
    const handleScroll = () => setScrolled(window.scrollY > 50);
    window.addEventListener('scroll', handleScroll);
    return () => window.removeEventListener('scroll', handleScroll);
  }, []);

  const profileData = {
    name: "Ajay Singh Chauhan",
    title: "Lead Technology Analyst | RPA & Cognitive Automation Expert",
    location: "Delhi, India",
    phone: "+91-9716250870",
    summary: "IT professional with 12.5 years of experience, including 8+ years specializing in Robotic Process Automation (RPA). Delivered 30+ enterprise solutions across Banking, Finance, and Logistics, saving 26,000+ annual hours and integrating LLMs for intelligent cognitive workflows.",
    skills: {
      rpa: ["Kofax RPA (10.3-11.5)", "Automation Anywhere (v10-v11)", "Kofax Kapow", "Kofax Management Console"],
      ai: ["ChatGPT / OpenAI API", "Cognitive Automation", "LLM Integration", "Intelligent Workflows"],
      tech: ["Python", "SQL", "JavaScript", "VBScript", "REST & SOAP APIs"],
      cloud: ["Azure Basics", "AWS Basics", "Big Data (HDFS, Hive, Pig)"]
    },
    experience: [
      {
        company: "DIENSTEN TECH LTD. / DBSCHENKER",
        role: "Lead Technology Analyst",
        period: "Jan 2021 - Dec 2025",
        highlights: [
          "Reduced manual effort by 70% through Global KPI reporting bots.",
          "Integrated ChatGPT API with Kofax RPA to process unstructured data (emails, free text).",
          "Automated reporting saving 2,000+ hours annually with 99% accuracy.",
          "Designed intelligent workflows combining RPA and LLMs for exception handling."
        ]
      },
      {
        company: "IBM India Pvt Ltd",
        role: "Technical Specialist (RPA Developer)",
        period: "Jan 2017 - Jan 2021",
        highlights: [
          "Automated Outward Remittance workflows, reducing TAT by 60%.",
          "Delivered automation saving 8 FTEs annually for MUFG.",
          "Reduced financial transaction errors by 35% via automated validations.",
          "Created reusable snippets reducing development time by 25%."
        ]
      },
      {
        company: "InfoZech Software Pvt Ltd",
        role: "Senior Software Engineer",
        period: "Nov 2015 - Jan 2017",
        highlights: [
          "Leveraged Big Data stack (HDFS, Hive, Pig) for telecom revenue forecasting.",
          "Optimized billing workflows reducing approval cycles by 30%.",
          "Engineered high-performance ETL processes for Oracle production environments."
        ]
      },
      {
        company: "NIIT Technologies Ltd",
        role: "Software Engineer",
        period: "Jul 2013 - Oct 2015",
        highlights: [
          "Developed Toyota Motors Thailand Dealer Distribution Management System.",
          "Specialized in Oracle Forms, Reports, and PL/SQL development.",
          "Built attendance and overtime systems using Java and SQL."
        ]
      }
    ],
    education: [
      { degree: "MCA", institution: "GGSIPU-RDIAS", score: "80.2%" },
      { degree: "B.Sc. Applied Physical Sciences (CS)", institution: "Delhi University", score: "65.5%" }
    ],
    certifications: [
      "Certified Kofax Technical Solution Specialist (RPA 10.4)",
      "Automation Anywhere Advanced & Master RPA Professional",
      "Python Programming Expert"
    ]
  };

  const TabButton = ({ id, label, icon: Icon }) => (
    <button
      onClick={() => setActiveTab(id)}
      className={`flex items-center gap-2 px-6 py-3 rounded-full transition-all duration-300 ${
        activeTab === id 
        ? 'bg-blue-600 text-white shadow-lg shadow-blue-500/30' 
        : 'hover:bg-gray-100 text-gray-600'
      }`}
    >
      <Icon size={18} />
      <span className="font-medium">{label}</span>
    </button>
  );

  return (
    <div className="min-h-screen bg-slate-50 text-slate-900 font-sans selection:bg-blue-100 selection:text-blue-600">
      {/* Navigation */}
      <nav className={`fixed top-0 w-full z-50 transition-all duration-300 ${scrolled ? 'bg-white/80 backdrop-blur-md shadow-sm py-3' : 'bg-transparent py-6'}`}>
        <div className="max-w-6xl mx-auto px-6 flex justify-between items-center">
          <div className="text-xl font-bold bg-gradient-to-r from-blue-600 to-indigo-600 bg-clip-text text-transparent">
            ASC.PRO
          </div>
          <div className="flex gap-4">
            <a href={`tel:${profileData.phone}`} className="p-2 hover:bg-blue-50 rounded-full transition-colors"><Phone size={20} className="text-blue-600"/></a>
            <a href="mailto:ajay@example.com" className="p-2 hover:bg-blue-50 rounded-full transition-colors"><Mail size={20} className="text-blue-600"/></a>
          </div>
        </div>
      </nav>

      {/* Hero Section */}
      <section className="pt-32 pb-20 px-6">
        <div className="max-w-6xl mx-auto flex flex-col md:flex-row items-center gap-12">
          <div className={`flex-1 transition-all duration-1000 transform ${isVisible ? 'translate-y-0 opacity-100' : 'translate-y-10 opacity-0'}`}>
            <div className="inline-flex items-center gap-2 px-3 py-1 rounded-full bg-blue-100 text-blue-700 text-sm font-medium mb-6">
              <Sparkles size={14} /> Available for Senior RPA Leadership
            </div>
            <h1 className="text-5xl md:text-7xl font-extrabold tracking-tight mb-6 leading-tight">
              Crafting <span className="text-blue-600">Digital</span> <br /> Workforce Excellence.
            </h1>
            <p className="text-xl text-slate-600 mb-8 max-w-2xl leading-relaxed">
              {profileData.summary}
            </p>
            <div className="flex flex-wrap gap-4">
              <button className="px-8 py-4 bg-slate-900 text-white rounded-xl font-bold hover:bg-blue-600 transition-all transform hover:-translate-y-1 shadow-xl shadow-slate-200">
                Contact Me
              </button>
              <div className="flex items-center gap-2 px-6 py-4 border border-slate-200 rounded-xl font-semibold">
                <MapPin size={18} /> {profileData.location}
              </div>
            </div>
          </div>
          <div className={`flex-1 relative transition-all duration-1000 delay-300 ${isVisible ? 'scale-100 opacity-100' : 'scale-95 opacity-0'}`}>
            <div className="w-full aspect-square bg-gradient-to-br from-blue-500 to-indigo-700 rounded-3xl relative overflow-hidden shadow-2xl">
               {/* Abstract Background for Photo */}
               <div className="absolute inset-0 opacity-20">
                 <div className="absolute top-10 left-10 w-32 h-32 bg-white rounded-full blur-3xl"></div>
                 <div className="absolute bottom-10 right-10 w-48 h-48 bg-white rounded-full blur-3xl"></div>
               </div>
               <div className="absolute inset-0 flex items-center justify-center text-white/90">
                  <div className="text-center">
                    <Bot size={120} strokeWidth={1} />
                    <p className="mt-4 font-mono text-sm tracking-widest uppercase">Intelligent Automation</p>
                  </div>
               </div>
            </div>
            {/* Floating Badges */}
            <div className="absolute -bottom-6 -left-6 bg-white p-6 rounded-2xl shadow-xl border border-slate-100">
              <div className="text-3xl font-bold text-blue-600">12.5+</div>
              <div className="text-xs uppercase tracking-wider text-slate-500 font-bold">Years Experience</div>
            </div>
            <div className="absolute -top-6 -right-6 bg-white p-6 rounded-2xl shadow-xl border border-slate-100">
              <div className="text-3xl font-bold text-indigo-600">30+</div>
              <div className="text-xs uppercase tracking-wider text-slate-500 font-bold">Solutions Delivered</div>
            </div>
          </div>
        </div>
      </section>

      {/* Main Content Area */}
      <section className="bg-white py-20 px-6 border-t border-slate-100">
        <div className="max-w-6xl mx-auto">
          {/* Tab Navigation */}
          <div className="flex flex-wrap justify-center gap-2 mb-16 bg-slate-50 p-2 rounded-3xl w-fit mx-auto">
            <TabButton id="experience" label="Experience" icon={Briefcase} />
            <TabButton id="skills" label="Tech Stack" icon={Code2} />
            <TabButton id="education" label="Education" icon={GraduationCap} />
            <TabButton id="certs" label="Certifications" icon={Award} />
          </div>

          {/* Experience Tab */}
          {activeTab === 'experience' && (
            <div className="space-y-12">
              {profileData.experience.map((exp, idx) => (
                <div key={idx} className="group relative pl-8 border-l-2 border-slate-100 hover:border-blue-500 transition-colors pb-12 last:pb-0">
                  <div className="absolute -left-[9px] top-0 w-4 h-4 rounded-full bg-white border-2 border-slate-200 group-hover:bg-blue-600 group-hover:border-blue-600 transition-all"></div>
                  <div className="flex flex-col md:flex-row md:justify-between md:items-start mb-4">
                    <div>
                      <h3 className="text-2xl font-bold text-slate-800">{exp.role}</h3>
                      <p className="text-blue-600 font-semibold">{exp.company}</p>
                    </div>
                    <span className="inline-block px-4 py-1 mt-2 md:mt-0 rounded-lg bg-slate-100 text-slate-600 font-medium text-sm">
                      {exp.period}
                    </span>
                  </div>
                  <ul className="grid md:grid-cols-2 gap-4">
                    {exp.highlights.map((item, i) => (
                      <li key={i} className="flex gap-3 text-slate-600 leading-relaxed">
                        <ChevronRight className="shrink-0 text-blue-500 mt-1" size={16} />
                        {item}
                      </li>
                    ))}
                  </ul>
                </div>
              ))}
            </div>
          )}

          {/* Skills Tab */}
          {activeTab === 'skills' && (
            <div className="grid md:grid-cols-2 gap-8">
              <div className="p-8 bg-blue-50 rounded-3xl">
                <div className="flex items-center gap-3 mb-6">
                  <div className="p-3 bg-blue-600 rounded-2xl text-white"><Bot /></div>
                  <h3 className="text-xl font-bold">RPA & Cognitive</h3>
                </div>
                <div className="flex flex-wrap gap-2">
                  {[...profileData.skills.rpa, ...profileData.skills.ai].map((skill, i) => (
                    <span key={i} className="px-4 py-2 bg-white rounded-xl text-slate-700 font-medium shadow-sm">{skill}</span>
                  ))}
                </div>
              </div>
              <div className="p-8 bg-indigo-50 rounded-3xl">
                <div className="flex items-center gap-3 mb-6">
                  <div className="p-3 bg-indigo-600 rounded-2xl text-white"><Terminal /></div>
                  <h3 className="text-xl font-bold">Programming & Data</h3>
                </div>
                <div className="flex flex-wrap gap-2">
                  {[...profileData.skills.tech, ...profileData.skills.cloud].map((skill, i) => (
                    <span key={i} className="px-4 py-2 bg-white rounded-xl text-slate-700 font-medium shadow-sm">{skill}</span>
                  ))}
                </div>
              </div>
            </div>
          )}

          {/* Education Tab */}
          {activeTab === 'education' && (
            <div className="grid md:grid-cols-2 gap-6">
              {profileData.education.map((edu, i) => (
                <div key={i} className="p-8 border border-slate-100 rounded-3xl hover:shadow-xl transition-all">
                  <div className="text-blue-600 mb-4"><GraduationCap size={32} /></div>
                  <h3 className="text-xl font-bold mb-1">{edu.degree}</h3>
                  <p className="text-slate-600 mb-4">{edu.institution}</p>
                  <div className="inline-block px-4 py-1 bg-green-100 text-green-700 font-bold rounded-lg">{edu.score}</div>
                </div>
              ))}
            </div>
          )}

          {/* Certifications Tab */}
          {activeTab === 'certs' && (
            <div className="grid md:grid-cols-3 gap-6">
              {profileData.certifications.map((cert, i) => (
                <div key={i} className="p-6 bg-slate-50 rounded-2xl border border-slate-100 flex items-start gap-4">
                  <div className="shrink-0 p-2 bg-white rounded-lg shadow-sm"><Award className="text-amber-500" /></div>
                  <p className="font-semibold text-slate-700">{cert}</p>
                </div>
              ))}
            </div>
          )}
        </div>
      </section>

      {/* Stats/Highlight Section */}
      <section className="py-20 px-6 bg-slate-900 text-white overflow-hidden relative">
        <div className="absolute top-0 right-0 w-96 h-96 bg-blue-600/20 blur-[100px] rounded-full"></div>
        <div className="max-w-6xl mx-auto grid grid-cols-2 md:grid-cols-4 gap-8 text-center">
          <div>
            <div className="text-4xl font-bold mb-2">26K+</div>
            <p className="text-slate-400 text-sm uppercase tracking-widest">Annual Hours Saved</p>
          </div>
          <div>
            <div className="text-4xl font-bold mb-2">40%</div>
            <p className="text-slate-400 text-sm uppercase tracking-widest">Cost Reduction</p>
          </div>
          <div>
            <div className="text-4xl font-bold mb-2">99%</div>
            <p className="text-slate-400 text-sm uppercase tracking-widest">Accuracy Rate</p>
          </div>
          <div>
            <div className="text-4xl font-bold mb-2">LLM</div>
            <p className="text-slate-400 text-sm uppercase tracking-widest">Powered Cognitive Bots</p>
          </div>
        </div>
      </section>

      {/* Footer */}
      <footer className="py-12 px-6 border-t border-slate-100">
        <div className="max-w-6xl mx-auto flex flex-col md:flex-row justify-between items-center gap-6">
          <div className="flex items-center gap-2 font-bold text-lg">
             <div className="w-8 h-8 bg-blue-600 rounded-lg flex items-center justify-center text-white text-xs">A</div>
             Ajay Singh Chauhan
          </div>
          <div className="flex gap-8 text-sm font-medium text-slate-500">
            <a href="#" className="hover:text-blue-600 transition-colors">LinkedIn</a>
            <a href="#" className="hover:text-blue-600 transition-colors">GitHub</a>
            <a href="#" className="hover:text-blue-600 transition-colors">Download Resume</a>
          </div>
          <p className="text-slate-400 text-sm">© 2026 ASC Portfolio. Built with React & AI.</p>
        </div>
      </footer>
    </div>
  );
};

export default App;
