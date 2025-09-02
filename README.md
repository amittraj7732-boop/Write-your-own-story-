import { motion } from "framer-motion"; import { Card, CardContent } from "@/components/ui/card"; import { Button } from "@/components/ui/button";

export default function HomePage() { return ( <div className="min-h-screen flex flex-col bg-gray-50 text-gray-800"> {/* Header */} <header className="bg-gray-900 text-white py-6 shadow-md"> <div className="container mx-auto text-center"> <h1 className="text-3xl font-bold">Nikhil Content Solutions</h1> <p className="mt-2 text-gray-300"> Professional Writing • Copywriting • Storytelling </p> </div> </header>

{/* Navigation */}
  <nav className="bg-gray-800 py-3">
    <div className="container mx-auto flex justify-center space-x-6">
      <a href="#services" className="text-gray-200 hover:text-white">Services</a>
      <a href="#portfolio" className="text-gray-200 hover:text-white">Portfolio</a>
      <a href="#about" className="text-gray-200 hover:text-white">About</a>
      <a href="#profile" className="text-gray-200 hover:text-white">Profile</a>
      <a href="#contact" className="text-gray-200 hover:text-white">Contact</a>
    </div>
  </nav>

  {/* Hero */}
  <motion.section
    className="flex flex-col items-center justify-center text-center py-20 bg-gray-100"
    initial={{ opacity: 0, y: 50 }}
    animate={{ opacity: 1, y: 0 }}
    transition={{ duration: 0.8 }}
  >
    <h2 className="text-4xl font-bold mb-4">
      Words That Work. Stories That Sell.
    </h2>
    <p className="max-w-2xl text-lg text-gray-600">
      Helping brands, businesses, and creators find their voice through compelling content.
    </p>
    <Button className="mt-6 text-lg px-6 py-3">Get Started</Button>
  </motion.section>

  {/* Services */}
  <section id="services" className="py-16 container mx-auto">
    <h2 className="text-3xl font-bold text-center mb-10">Services</h2>
    <div className="grid grid-cols-1 md:grid-cols-3 gap-6">
      {[
        {
          title: "Content Writing",
          desc: "SEO-friendly articles, blogs, and web content tailored to your brand’s tone.",
        },
        {
          title: "Ad Copy",
          desc: "Catchy, persuasive copy for ads, social media, and campaigns that convert.",
        },
        {
          title: "Manga & Storytelling",
          desc: "Engaging plots, scripts, and character-driven stories for manga & creative projects.",
        },
      ].map((service, i) => (
        <motion.div
          key={i}
          initial={{ opacity: 0, y: 30 }}
          whileInView={{ opacity: 1, y: 0 }}
          viewport={{ once: true }}
          transition={{ delay: i * 0.2 }}
        >
          <Card className="shadow-md rounded-2xl">
            <CardContent className="p-6">
              <h3 className="text-xl font-semibold mb-2">{service.title}</h3>
              <p className="text-gray-600">{service.desc}</p>
            </CardContent>
          </Card>
        </motion.div>
      ))}
    </div>
  </section>

  {/* Portfolio */}
  <section id="portfolio" className="py-16 bg-white">
    <div className="container mx-auto">
      <h2 className="text-3xl font-bold text-center mb-10">Portfolio</h2>
      <div className="grid grid-cols-1 md:grid-cols-3 gap-6">
        {[
          { title: "Blog Article", desc: "In-depth SEO blog for a tech company." },
          { title: "Ad Campaign Copy", desc: "High-conversion ad copy for social media." },
          { title: "Manga Script", desc: "Storyboarding and dialogue for a manga project." },
        ].map((item, i) => (
          <motion.div
            key={i}
            initial={{ opacity: 0, y: 30 }}
            whileInView={{ opacity: 1, y: 0 }}
            viewport={{ once: true }}
            transition={{ delay: i * 0.2 }}
          >
            <Card className="shadow-md rounded-2xl">
              <CardContent className="p-6">
                <h3 className="text-xl font-semibold mb-2">{item.title}</h3>
                <p className="text-gray-600">{item.desc}</p>
              </CardContent>
            </Card>
          </motion.div>
        ))}
      </div>
    </div>
  </section>

  {/* About */}
  <section id="about" className="py-16 bg-gray-100">
    <div className="container mx-auto max-w-3xl text-center">
      <h2 className="text-3xl font-bold mb-6">About Me</h2>
      <p className="text-gray-700 text-lg">
        I’m Nikhil, a freelance content writer specializing in ad copy, manga writing, and storytelling. I help brands and creators communicate their ideas with clarity and creativity.
      </p>
    </div>
  </section>

  {/* Profile */}
  <section id="profile" className="py-16 container mx-auto">
    <h2 className="text-3xl font-bold text-center mb-10">Profile</h2>
    <div className="flex flex-col md:flex-row items-center md:space-x-10">
      <img
        src="/profile.jpg"
        alt="Profile"
        className="w-40 h-40 rounded-full shadow-md mb-6 md:mb-0"
      />
      <div>
        <h3 className="text-2xl font-semibold mb-2">Nikhil Thakur</h3>
        <p className="text-gray-700 mb-4">
          Freelance Content Writer • Copywriter • Storyteller
        </p>
        <div className="flex flex-wrap gap-2">
          {["SEO Writing", "Ad Copy", "Manga Scripts", "Brand Storytelling", "Creative Writing"].map((skill, i) => (
            <span key={i} className="px-3 py-1 bg-blue-100 text-blue-700 rounded-full text-sm">
              {skill}
            </span>
          ))}
        </div>
      </div>
    </div>
  </section>

  {/* Contact */}
  <section id="contact" className="py-16 container mx-auto text-center">
    <h2 className="text-3xl font-bold mb-6">Contact</h2>
    <form
      action="https://formspree.io/f/your-form-id"
      method="POST"
      className="max-w-lg mx-auto bg-white p-6 rounded-2xl shadow-md space-y-4"
    >
      <input
        type="text"
        name="name"
        placeholder="Your Name"
        className="w-full p-3 border rounded-lg focus:outline-none focus:ring-2 focus:ring-blue-500"
        required
      />
      <input
        type="email"
        name="email"
        placeholder="Your Email"
        className="w-full p-3 border rounded-lg focus:outline-none focus:ring-2 focus:ring-blue-500"
        required
      />
      <textarea
        name="message"
        placeholder="Your Message"
        rows="4"
        className="w-full p-3 border rounded-lg focus:outline-none focus:ring-2 focus:ring-blue-500"
        required
      ></textarea>
      <Button type="submit" className="w-full py-3 text-lg">Send Message</Button>
    </form>
    <p className="text-gray-700 mt-6">Or email me directly at <a href="mailto:nikhil@example.com" className="text-blue-600 hover:underline">nikhil@example.com</a></p>
  </section>

  {/* Footer */}
  <footer className="bg-gray-900 text-white text-center py-6 mt-auto">
    <p>&copy; 2025 Nikhil Content Solutions. All rights reserved.</p>
  </footer>
</div>

); }
