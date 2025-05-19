""import { motion } from 'framer-motion'; import { useState } from 'react'; import { Button } from '@/components/ui/button';

export default function EarthquakePunch() { const [activated, setActivated] = useState(false);

const handleActivate = () => { setActivated(true); setTimeout(() => setActivated(false), 2000); };

return ( <div className="flex flex-col items-center justify-center h-screen bg-gray-800 text-white relative overflow-hidden"> <Button className="mb-4" onClick={handleActivate}> Yumruk Nefesi: 7. Form - Deprem Yumruğu! </Button>

<motion.div
    animate={activated ? { scale: [1, 1.5, 1], rotate: [0, 10, -10, 0] } : {}}
    transition={{ duration: 0.5 }}
    className={`w-40 h-40 bg-red-500 rounded-full ${activated ? 'shadow-lg' : ''}`}
  />

  <motion.div
    initial={{ opacity: 0 }}
    animate={activated ? { opacity: [0, 1, 0], scale: [1, 1.5, 1] } : {}}
    transition={{ duration: 1 }}
    className="mt-5 text-xl"
  >
    Zemin sarsılıyor!
  </motion.div>

  {activated && (
    <motion.div
      initial={{ scale: 0 }}
      animate={{ scale: [0, 1.2, 1], opacity: [1, 0.5, 0] }}
      transition={{ duration: 1 }}
      className="absolute w-[500px] h-[500px] bg-gray-600 opacity-20 rounded-full"
      style={{ top: '50%', left: '50%', transform: 'translate(-50%, -50%)' }}
    />
  )}
</div>

); } ""

